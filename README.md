<p align="center">
  <img src="./us-intl.png" />
</p>

# <p align="center">United States (Reformed International)</p>
<p align="center">A sensible version of the US-International keyboard layout with AltGr dead keys for Windows, Mac, and Linux.</p>

## Table of Contents
  - [The Problem](#the-problem)
  - [The Standard](#the-standard)
  - [The Reform](#the-reform)
  - [Orthographic Compatibility](#orthographic-compatibility)
  - [Installation](#installation)
    - [Windows](#windows)
      - [KLC (Recommended, no 3rd party software required)](#klc-recommended-no-3rd-party-software-required)
      - [AutoHotkey](#autohotkey)
      - [PKL](#pkl)
    - [Mac](#mac)
      - [Keylayout](#keylayout)
    - [Linux](#linux)
      - [XKB](#xkb)
  - [Credits](#credits)

## The Problem
I originally made this layout because included Windows keyboard layout for United States (International) is subpar. Here is a list of things the Windows US-International layout does not have that are usually included in layouts such as the one included in X on Linux:
* The `œ` ligature
* Left and right facing quotation marks `“` `”`
* The breve, caron, double acute, ogonek, macron, overdot, underdot, and overring diacritical marks
* The lack of the option for dead keys activated by `AltGr`, which means that single symbols that are also used as diacritical marks such as the `'` must be typed with a following `Space`

There was a very noble attempt to fix this madness by fellow GitHub user [thomasfaingnaert](https://github.com/thomasfaingnaert/win-us-intl-altgr). However, it only addresses the last problem, does not contain a copyleft-friendly license, and does not map a large number of precomposed letters with diacritics in Unicode.

But upon looking at the way US-International tends to be done, I realized some of its inefficiencies and nonsensical mappings. 
### Therefore, I decided to reform the entire layout. And due to the changes I made, I also decided to make this layout cross-platform!

## The Standard
This is the way that US-International is usually done in the Linux sphere and such, and will be compared against below:

![US-International](./us-intl.png)
## The Reform
![US-Reformed-International](./us-intl.png)

This is my keyboard layout that aims to fix the problems with given US-International implementations. Here is a list of the changes with their justifications:
* `ł` and `Ł` replace `ø` and `Ø` at `AltGr`+`l` and `AltGr`+`Shift`+`l` respectively.
  * Polish has around 50 million speakers, and although their orthography may be suboptimal from a contemporary perspective, it is used enough to win a spot on the keyboard, naturally at `l` due to it being `l` with a stroke.
* `ø` and `Ø` at `AltGr`+`l` and `AltGr`+`Shift`+`l` respectively replace `ö` and `Ö` at `AltGr`+`p` and `AltGr`+`Shift`+`p` respectively.
  * US-International has common precomposed letters with diacritics nearing common letters, and `ó` and `ø` seem like reasonably common shortcuts, satisfying most speakers of Romance and Germanic languages. 
* `ö` and `Ö` at `AltGr`+`p` and `AltGr`+`Shift`+`p` respectively are omitted.
  * Although `ö` and `Ö` are pretty common, it is justifiable to remove them due to the previous two change justifications, space constraints, and the fact that `ö` and `Ö` can still be typed with `AltGr`+`Shift`+`'` followed by `o` and `AltGr`+`Shift`+`'` followed by `Shift`+`o` respectively.
* Macron at `AltGr`+`Shift`+`3` replaces underdot at `AltGr`+`Shift`+`-`.
  * The `-` looks very similar to the macron, hence why it is only natural to put it as a modifier on the same key.
* Underdot at `AltGr`+`Shift`+`-` replaces overdot at `AltGr`+`.`.
  * The `.` is very similar to the underdot, hence why it is only natural to put it as a modifier on the same key.
* Overdot at `AltGr`+`.` replaces caron at `AltGr`+`Shift`+`.`.
  * Your shift key might have an arrow facing up on it. Think of the shift key as moving the underdot from below the letter in the direction that arrow points, up! Overdot!
* Caron at `AltGr`+`Shift`+`.` is moved to `AltGr`+`Shift`+`5`.
  * The caron is also sometimes called an inverted circumflex. Because of this, it seems only natural that the inverted circumflex should go right next to the normal circumflex (at `AltGr`+`Shift`+`6`).
* Cedilla is added to `AltGr`+`Shift`+`7`.
  * The Cedilla is used in some common languages such as French (~77 million speakers) and Portugese (~223 million speakers), which is nothing to sneeze at. It is somewhat similar looking to the ogonek (at `AltGr`+`Shift`+`8`), so it was put right next to it.
* Dead currency is added to `AltGr`+`Shift`+`4`.
  * This lets you type many different currency symbols! Check the source files for the mappings.
* `£` is moved from `AltGr`+`Shift`+`4` to `AltGr`+`4`.
  * See above. The dead keys on this row are all on `AltGr`+`Shift` modifiers.
* Solidus is added to `AltGr`+`Shift`+`/`.
  * The keyboard already has a `/` key, and many languages and currency symbols across the world use letters with a solidus diacritic.
* `™` replaces `®` at `AltGr`+`Shift`+`r`.
  * The `®` is already at `AltGr`+`r`. Replacing it fixes the fact that it is redundant. `™` was its successor because of the fact that we often say "Registered Trademark" in the Anglosphere, and for meme value.
* Non-breaking space (`NBS`) and Zero-width space (`ZWS`) are added to `AltGr`+`Space` and `AltGr`+`Shift`+`Space` respectively.
  * These are some fun and sometimes quite useful characters. Being spaces, it only makes sense to include them on the `Space` key.
* Combination diacritical marks are added to a given dead dead key combination followed by `Space`
  * Most of the time, `Space` following a dead key combination prints the spacing character for the diacritical mark the dead key is used for. This is not very useful, because most dead keys such as `~` and `'` have their own non-dead key combination and can be typed anyway. It also locks out the possibility of putting the diacritics on leters that would otherwise not have a precomposed entry in Unicode. For example, n-diaeresis (`n̈`) is not a precomposed character in Unicode. With the Reformed layout, it can be typed with `n` followed by `AltGr`+`Shift`+`'` followed by `Space`. This is technically two characters, but it looks completely natural due to Unicode's combination diaeresis character. This feature can also be used to type letters with multiple diacritics. You can even get as crazy as `ņ̨̣̃́̈̄̌̂̆̊̇` if you so truly wish!
* Spacing diacritical marks are typed with a given dead key combination followed by `NBS`
  * These are arguably used less than combination characters (outside of talking about the diacritical marks themselves), and they're still nice to be able to type
* **Dead keys are only activated by `AltGr`**
  * This is what I was talking about earlier with AltGr dead keys. It's the only sensible way to have dead keys.

## Orthographic Compatibility
Hopefully, these changes make typing with various diacritics and non-English orthographies easier. This keyboard layout as a result is compatible with over 170 languages that use the Latin alphabet!
Here is a (imperfect) list of languages and dialects using the Latin alphabet. They're grouped alphabetically into 3 catagories based on their orthographies' compatability with this keyboard layout: `Fully Compatible`, `Effectively Compatible`, and `Incompatible`.
<details>
  <summary>Click to expand</summary>

### Fully Compatible:
* Acehnese, Achomi (Larestani, Khodmooni), Afar, Albanian, Aragonese, Arbëresh, Aromanian (Vlach), Asturian, Australian Kriol, Austro-Bavarian, Aymara, Banjar, Basque, Belarusian, Bislama, Bosnian-Serbian-Croatian (Serbo-Croatian), Bourbonnais Creole (Mascarene, Agalega, Chagossian, Mauritian, Réunion, Rodriguan, Seychellois), Breton, Brithenig, Cebuano, Chamorro, Cherokee, Cornish, Corsican, Cree, Czech, Dalecarlian, Danish, Dutch, Emilian-Romagnol (Emiliano-Romagnol), English, Esperanto, Estonian, Extremaduran, Fala, Faroese, Fijian, Finnish, Flemish, French, Frisian, Friulian (Friulan), Gagauz, Galacian, German, Greenlandic, Guarani, Gwich'in, Haitian Creole, Hawaiian, Hiri Motu (Police Motu, Hiri), Hmong / Mong (RPA), Hungarian, Hän, Icelandic, Ido, Igbo, Ilocano (Ilokano), Indonesian, Innu-aimun (Montagnais), Interglossa, Interlingua, Interlingue, Irish, Italian, Javanese, Judeo-Spanish, Kalau Lagau Ya (Kalaw Lagaw Ya, Kala Lagaw Ya), Karelian, Kashubian (Cassubian), Khasi, Kikuyu (Gikuyu), Kinyarwanda, Kirundi (Rundi), Klingon, Kongo (Kikongo), Konkani, Kotava, Kurdish, Latin, Latvian, Leonese, Lingua Franca Nova, Lingwa de Planeta, Lithuanian, Livonian, Lojban, Luxembourgish, Láadan, Malagasy, Malay, Maltese, Manx, Marshallese (Ebon), Massachusett, Minangkabau, Mirandese, Mohawk, Moldovan, Māori, Na'vi, Nahuatl (Mexicano), Nauruan, Navajo, Ndebele (isiNdebele), Neo, Nias, Niuean, Norn, Norwegian, Nothern Sotho, Novial, Occitan, Oromo, Otomi, Palauan, Papiamento, Picard, Piedmontese, Polish, Portuguese, Quechuan (Runasimi), Quenya, Rhaeto-Romance (Rheto-Romance, Rhaetian), Rohingya (Ruáingga), Romani, Romansh, Samoan, Sardinian (Sard), Sasak, Scottish Gaelic (Scots Gaelic), Shona, Sicilian, Sindarin, Slovak, Slovenian (Slovene), Sorbian, Southern Sami, Spanish, Sundanese, Swahili, Swedish, Tagalog (Filipino, Pilipino), Tahitian, Talossan, Tetum, Toki Pona, Tok Pisin, Tokelauan, Tongan, Torres Strait Creole, Tsonga (Xitsonga), Tswana, Turkmen, Tuscan, Ulithian, Ume Sami, Uyghur (Uighur), Veps, Võro, Vötgil, Walloon, Welsh, Wolof, Xhosa (isiXhosa), Yapese, Yoruba (Nigeria), Zaza, Zulu (isiZulu), Zuni

### Effectively Compatible:
* Afrikaans
  * Afrikaans has characters such as `ŉ`, which is a depcrecated codepoint in Unicode and is actively recommended to be appoximated with `'n`.
* Anglo-Norman
  * Yogh (`Ȝ ȝ`) evolved into `gh` in Modern English words such as "night", hence why some modern scholars approxmate it with `gh`.
* Anglo-Saxon
  * Wynn (`Ƿ ƿ`) evolved into `w` and can be appoximated as such.
* Catalan
  * Use `AltGr`+`Shift`+`.` followed by `L` or `l` to type `Ŀ` or `ŀ` respectively.
* Poliespo
  * Poliespo's custom overlapping letters are not included in Unicode at all and are therefore impossible to type on any keyboard layout. Feel free to approximate them any way you wish.
* Romanian
  * This keyboard is only able to type `Ş` and `Ţ` instead of `Ș` and `Ț`, so the latter must be appoximated by the former. These are officially different letters, but some fonts render them exactly the same, so it's a reasonable approximation. The letters with cedillas also appear in some older Romanian texts.
* Uzbek
  * The Uzbek orthography seems to be currently in a state of discombobulation. Tread lightly.
* Volapük
  * Schleyer's original letters are indeed in Unicode but are unable to be typed using this keyboard layout. This is fine because the replacement versions with diacritics (or digraphs) are canonically accepted.
### Incompatible:
* Afrihili, Azerbaijani, Bambara, Berber, Crimean, Cypriot Arabic (Sanna), Dinka, Fula, Hausa, Inari Sami, Ithkuil, Kay(f)bop(t), Kazakh, Kēlen, Laz, Lingala, Luganda, Lule Sami, Northern Sami, Skolt Sami, Tatar, Tunisian Arabic, Turkish, Turoyo, Venda, Vietnamese, Yoruba (Benin)
</details>

---

# Installation
## Windows
Pick **one** (1) of the install methods below
### KLC (**Recommended**, no 3rd party software required)
  **United States**: Download the latest `klc.zip` from [the releases tab of this repo](https://github.com/barkloaf/US-Reformed-International/releases). Extract it and run `Setup.exe` from the resulting folder.
  To apply the layout, go to Windows settings > `Time & Language` > `Language` > `English (United States)` > `Options` > `Add a keyboard` > `United States (Reformed International)`

  **Netherlands:** If you wish to install the layout to the `nl-NL` locale, download the latest `klc-nl.zip` from [the releases tab of this repo](https://github.com/barkloaf/US-Reformed-International/releases). Extract it and run `Setup.exe` from the resulting folder. To apply the layout, go to Windows settings > `Tijd en Taal` > `Taal` > `Nederlands (Nederland)` > `Opties` > `Een toetsenbord toevoegen` > `Verenigde Staten (gewijzigd internationaal)`

  **Other locales:** `klc.zip` installs to the `en-US` locale. If you wish to install the layout to a different locale:
  1. Download the source code file [`klc/us-refor.klc`](https://github.com/barkloaf/US-Reformed-International/blob/master/klc/us-refor.klc)
  2. Open the source code file [Microsoft Keyboard Layout Creator](https://www.microsoft.com/en-us/download/details.aspx?id=102134)
  3. Edit the language in `Project` > `Properties...` > `Language`
     * **Note:** MSKLC will not compile the layout if it shares a name with an existing keyboard on your system. The name of the layout can also be changed in this menu if necessary. 
  4. Create the installer by going to `Project` > `Build DLL and Setup Package`
  5. Run `Setup.exe` from the resulting folder.
  6. Apply the layout in Windows settings > `Time & Language` > `Language` > (Language name) > `Options` > `Add a keyboard` > `United States (Reformed International)`

### AutoHotkey
  Presuming [AutoHotkey](https://www.autohotkey.com) is installed, download the latest `ahk.zip` from [the releases tab of this repo](https://github.com/barkloaf/US-Reformed-International/releases). Extract it and run `us-refor.ahk` from the folder.

  **Note:** This version of the layout is untested. If there are any issues, please document them on the [issues page](https://github.com/barkloaf/US-Reformed-International/issues).

### PKL
  Download the latest `pkl.zip` from [the releases tab of this repo](https://github.com/barkloaf/US-Reformed-International/releases). Extract it and run `pkl.exe` from the folder.

  **Note:** This version of the layout is untested. If there are any issues, please document them on the [issues page](https://github.com/barkloaf/US-Reformed-International/issues).

## Mac
### Keylayout
  Download the latest `keylayout.tar.gz` from [the releases tab of this repo](https://github.com/barkloaf/US-Reformed-International/releases). Extract it and run `install-system.sh` or `install-user.sh` from the folder.

  **Note:** The `AltGr` key on Macs is either `Option` key.

## Linux
### XKB
  Download the latest `xkb.tar.gz` from [the releases tab of this repo](https://github.com/barkloaf/US-Reformed-International/releases). Extract it and run `install-system.sh` as root followed by `scripts/install-user.sh` as user from the folder. The layout might need to be enabled first in order to be used. This may vary per distribution.

# Credits
  The auto-generated files and scripts in this repo were created by [`klfc`](https://github.com/39aldo39/klfc)!