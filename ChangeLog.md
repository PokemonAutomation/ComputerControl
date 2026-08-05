**Version 0.69.7 (private beta):**
- All OCR text recognition now uses the PaddleOCR library. (credit jw)
- Partially rewritten SwSh Egg Autonomous to improve reliability. (credit jw)
- Added Pokopia Daily Farmer. (credit Gimikyu)
- Large tables and option groups are collapsed by default to improve loading times.
- Improved reliability of FRLG RNG programs. (credit Astro)
- Removed extraneous options from FRLG RNG programs. (credit Astro)
- Improve stability of Home Sorter. (repoted by Tethys, credit dolphincurry)
- PABotBase1 is now hidden by default. If you still need it, you need to turn it on in the settings.

The OCR change from Tesseract to PaddleOCR is a very big and dangerous change. Lots of stuff broke and were fixed during testing and there's likely more that we missed. Please let us know if you encounter any issues.

As part of this migration, both Tesseract and PaddleOCR are included in this release - thus the larger download size. You can choose which to use and can rollback to Tesseract if you encounter any issues. In the next release, Tesseract will no longer be included and will require a separate resource download. This will reduce download sizes again.

External resource downloading is a new feature we will be pushing soon that will allow us to have very large resources while keeping the main CC download reasonably small. Thus we will be free to build and use large ML models in the future.
