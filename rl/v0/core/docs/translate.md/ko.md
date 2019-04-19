# 한글화 번역을 함께 해보세요.

PXT supports localized content for both PXT web app and target documentation. The default language is currently always English.

Our translations are managed via Crowdin, a translation management platform. It is free to join and you can volunteer to translate parts of the web site.

## Crowdin project

The project below contains the resources from https://makecode.com and the menu items of @homeurl@.

* <https://crowdin.com/project/kindscript>

If you want to help translating the editor, please sign in to Crowdin and send us a translator request.

### ~ hint

Looking to help translate **microbit.org**? Try http://translate.microbit.org/ to help the Microbit Foundation!

### ~

## 실시간 번역

To test your changes "live", use **beta** build and the `#liveforcelang=CODE` hash argument where `CODE` is your language ISO code. For example, to see the french translations:

* https://pxt.microbit.org/beta?liveforcelang=fr

Note that there may be a delay of up to 5 minutes before your changes in Crowdin make it into the "live" view. Also, the language will only be available in the editor's language selection if the target has enabled that locale - which is why you need to use the hash mentioned above.

## Translating the editor interface

All the editor interface strings, like the "Download" button are in the `strings.json` file.

## Translating the blocks and reference documentation

You will find target specific localization files under folders in crowdin. For example, all blocks, reference translations for the **microbit** are under `/microbit` , one for the block definition and one for the descriptions:

* `core-strings.json`: contains the block definitions
* `core-jsdoc-strings.json`: contains the descriptions

The block definition should be carefully translated using the [block definition syntax](https://makecode.com/defining-blocks). Open the developer tools and watch the console, PXT wil validate the localized string and flag potential issues.

### Block localization guidance

* 블록에 대문자를 사용하지 마세요.
* `%variable` 이름을 번역하지 마세요.
* 매개 변수 순서를 바꾸지 마세요.
* 똑같은 구조로 `|`, `%variables%` 기호를 유지하세요.

## Translating Target specific strings

The `pxtarget.json` file contains a number of strings which show up on doc pages (mostly menu items and target name). These strings are uploaded as the `targetid/target-strings.json` file in Crowdin and loaded by the editor on demand.

## Translating Documentation

Translation of documentation pages are pulled from crowdin by the cloud backend automatically.