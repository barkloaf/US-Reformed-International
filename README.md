# United States (Reformed International)
A sensible version of the US-International keyboard layout for Windows, including with AltGr dead keys
## The Problem
The included Windows keyboard layout for United States (International) is subpar. Here is a list of things the Windows US-International layout does not have that are usually included in layouts such as the one included on Linux:
* The `œ` ligature
* Left and right facing quotation marks `“` `”`
* The breve, caron, double acute, ogonek, macron, overdot, underdot, and overring diacritical marks
* The lack of the option for dead keys activated by `AltGr`, which means that single symbols that are also used as diacritical marks such as the `'` but be followed by a space

There was a very noble attempt to fix this madness by fellow GitHub user [thomasfaingnaert](https://github.com/thomasfaingnaert/win-us-intl-altgr). However, it only addresses the last problem, does not contain a copyleft-friendly license, and does not map a large number of precomposed letters with diacritics in Unicode.

But upon looking at the way US-International tends to be done, I realized some of its inefficiencies and nonsensical mappings. Therefore, I decided to reform the entire layout...
## The Standard
This is the way that US-International is usually done in Linux and such, and will be compared against below:
![US-International](https://wildcard.yiff.church/i/im1h033s.png)
## The Reform
![US-Reformed-International](https://wildcard.yiff.church/i/c32j7ae0.png)

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
* Solidus is added to `AltGr`+`Shift`+`/`.
  * The keyboard already has a `/` key, and many languages and currency symbols across the world use letters with a solidus diacritic.
* Dead keys are only activated by `AltGr`
  * This is what I was talking about earlier with AltGr dead keys. It's the only sensible way to have dead keys.
* Combination diacritical marks are added to a given dead dead key combination +`Space`
  * Most of the time, `Space` following a dead key combination prints the spacing character for the diacritical mark the dead key is used for. This is not very useful, because most dead keys such as `~` and `"` have their own non-dead key combination and can be typed anyway. It also locks out the possibility of putting the diacritics on leters that would otherwise not have a precomposed entry in Unicode. For example, n-diaeresis (`n̈`) is not a precomposed character in Unicode. With the Reformed layout, it can be typed with `n` followed by `AltGr`+`Shift`+`'` followed by `Space`. This is technically two characters, but it looks completely natural due to Unicode's combination diaeresis character. This feature can also be used to type letters with multiple diacritics. You can even get as crazy as `ņ̨̣̃́̈̄̌̂̆̊̇` if you so truly wish!
  
Hopefully, these changes make typing with various diacritics and non-English orthographies easier.
## Installation
Download the latest `us-refor.zip` on [the releases tab of this repo](https://github.com/barkloaf/US-Reformed-International/releases). Extract it and run `Setup.exe`.

Alternatively, you may download the source code file and open it in [Microsoft Keyboard Layout Creator](https://www.microsoft.com/en-us/download/details.aspx?id=22339). An installer is created by going to `Project`>`Build DLL and Setup Package`. Run `Setup.exe` from the resulting folder.
