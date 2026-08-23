**Version 0.69.18 (beta):**
- OCR text recognition now uses the PaddleOCR library. (credit jw)
- Partially rewritten SwSh Egg Autonomous to improve reliability. (credit jw)
- Added Pokopia Daily Farmer. (credit Gimikyu)
- Large tables and option groups are collapsed by default to improve loading times.
- Various improvements to SV AutoStory. (reported by chris, credit jw)
- Fixed FRLG RNG programs failing on 4k. (reported by dolphincurry, credit Astro)
- Fixed Togepi RNG. (reported by thewhitewolfking and clap, credit Astro)
- Improved reliability of FRLG RNG programs. (credit Astro)
- Fixed FRLG daycare pickup. (reported by Patrick, credit Astro)
- Removed extraneous options from FRLG RNG programs. (credit Astro)
- Improve stability of Home Sorter. (repoted by Tethys, credit dolphincurry)
- Improved fault tolerance of Donut Maker.
- Image processing is now done using OpenCV instead of Qt.
- PABotBase1 is now hidden by default. If you still need it, you need to turn it on in the settings.

The migration from Tesseract to PaddleOCR for text recognition is a very big and dangerous change. Lots of stuff broke and were fixed during testing and there's likely more that we missed. Please let us know if you encounter any issues.

As part of this migration, both Tesseract and PaddleOCR are included in this release - thus the larger download size. You can choose which to use and can rollback to Tesseract if you encounter any issues. In the next release, Tesseract will no longer be included and will require a separate resource download. This will reduce download sizes again.

External resource downloading is a new feature we will be pushing in v0.70 that will allow us to have very large resources while keeping the main CC download reasonably small. Thus we will be free to build and use large ML models in the future.
