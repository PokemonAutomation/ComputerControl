# OCR

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

OCR is for optical character recognition, technique to read texts from images.
We use [Tesseract library](https://github.com/tesseract-ocr/tesseract) to do OCR.
Given a video screen image, we first create a crop to get the region of the image where text is. See [this topic](SubImage.md) on how to get a region of the image. Then we apply our OCR functions on this sub-image.

We mostly use [`SmallDictionaryMatcher`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonTools/OCR/OCR_SmallDictionaryMatcher.h)
and [`LargeDictionaryMatcher`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonTools/OCR/OCR_LargeDictionaryMatcher.h)
to find a text match from a pre-difined set of candidate texts.

## SmallDictionaryMatcher

`SmallDictionaryMatcher` loads a JSON file (see the [JSON topic](JSON.md) for more details) in the resource folder. The JSON file contains texts of every language available in a Pokémon game. An example is [BerryNameOCR.json](https://github.com/PokemonAutomation/Packages/blob/master/SerialPrograms/Resources/Pokemon/BerryNameOCR.json). In this file, for each language ("eng", "jpn" and so on) , it stores the mapping from each berry slug (see the [slug topic](Slug.md) for more details) to its text in that language. For example, in English, the text for Cheri Berry (which slug is "cheri-berry") is "Cheri Berry", while in Japanese, the text is "クラボのみ". So we have
```
"eng": {
    "cheri-berry": [
        "Cheri Berry"
    ],
    ... (other berry's dictionary entries)
},
"jpn": {
    "cheri-berry": [
        "クラボのみ"
    ],
    ... (other berry's dictionary entries)
}
... (other languages)
```
[`BerryNameReader`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/Pokemon/Inference/Pokemon_BerryNameReader.h) loads this berry JSON into `SmallDictionaryMatcher` to read berry names.

## LargeDictionaryMatcher

`LargeDictionaryMatcher` loads several JSON files to build the dictionary. Each JSON file corresponds to one language. An example group of JSON files is [PokemonNameOCR](https://github.com/PokemonAutomation/Packages/tree/master/SerialPrograms/Resources/Pokemon/PokemonNameOCR). Because there are now many Pokémon, we split the OCR data into separate JSON files based on language:
```
PokemonOCR-fra.json:
{
    "abomasnow": [
        "Blizzaroi"
    ],
    ... (other Pokémon's dictionary entries in French)
}

PokemonOCR-chi_tra.json:
{
    "abomasnow": [
        "暴雪王",
        "繁霎王",
        "鬘粘王"
    ],
    ... (other Pokémon's dictionary entries in traditional Chinese)
}

... (other language JSON files)
```
[PokemonNameReader](https://github.com/PokemonAutomation/Packages/tree/master/SerialPrograms/Source/Pokemon/Inference/Pokemon_NameReader.h) loads this Pokémon name JSON folder to read Pokémon names.

## Multiple Text Values for One Slug
Note in the traditional Chinese JSON file, Abomasnow corresponds to three text values "暴雪王", "繁霎王" and "鬘粘王".
This is because Tesseract has a hard time detecting Asian language characters (Korean, traditional Chinese and simplified Chinese).
So we put those commonly misread results of Abomasnow ("繁霎王" and "鬘粘王") along with the correct text ("暴雪王") into the dictionary. When Tesseract reads it wrongly, we can still know it's Abomasnow.

Note: even with this trick, OCR can still sometimes fail, especially for Asian language characters. For most robust programs, we need to consider using other inferences (color, timing, sound) to supplement OCR.

## Read Text from Image

Both two matcher classes are based on [`DictionaryMatcher`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonTools/OCR/OCR_DictionaryMatcher.h), which provide function `match_substring_from_image_multifiltered()` to match a substring from an image.
See its comments for how to use it.

You can find out how `BerryNameReader` reads berry names in [**PokemonBDSP_GiftBerryReset**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonBDSP/Programs/Farming/PokemonBDSP_GiftBerryReset.cpp).

## Read Number from Image

We have a special function, [`OCR::read_number()`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonTools/OCR/OCR_NumberReader.h)
to read only numbers on an image.
See [**PokemonBDSP_BattleBallReader**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonBDSP/Inference/Battles/PokemonBDSP_BattleBallReader.cpp) as an example.


Note: same as our general text OCR functions, `OCR::read_number()` is not the most robust. It may occasionally fail to read the correct number. For most robust programs, we suggest using other inferences (color, timing, sound) to supplement OCR.
