# Barakunji (बारहकुंजी)
Barakunji is based on the clustering of syllables according to the area of the mouth used that is inherent to Devanagari and many other Indian scripts. There are 7 such clusters in total (8 if you count the conjuncts क्ष, त्र, ज्ञ as a separate cluster), with 5 having five consonants each, and 2 having four each. Thus, we get a character set of 33 consonants. In addition, there are 12 vowels, out of which 10 are actually part of a pair of short and long vowels.

We utilise these two facts - that there are upto 5 related consonants per consonant cluster, as well as that there are 10 pairs of short and long vowels, to be able to create a keyboard that encompasses nearly 50 characters (along with punctuation etc.) into only 12 keys. In addition, by adding numerous rules to the parser, we are able to correctly preserve the phonetic order of the characters and diacritics, something especially important for syllabic scripts (also known as *abugidas*) like Devanagari.

**Note:** Barakunji depends upon flick and multitap functionality which is only availble in Keyman 17.0 and above.


## Functionality and Usage
Each *akshara* key is equipped with the ability to produce not only the character on the key, but 3-8 other related characters from its cluster (i.e. *varga*). This is done by flicking the key in the direction of the desired character. For example, flicking the क key to the right will produce ख, flicking it up will produce ग, and so on. The characters available on flicking are displayed on the key itself. They are ordered in clockwise order **starting from the left**. For keys with more than 4 options, the order continues **from the top left corner of the key**.

Each of these options can also be accessed by holding the key for at least a second, which brings up a list of the available characters to choose from.

Finally, you can also cycle through the characters available by tapping on the key multiple times.

### Vowels (*Svara*)
Vowels and their diacritics play a central role in designating sounds to consonants in most Indian scripts. As such, the key for vowels is placed right in the center of the keyboard, for easier accessability.

If you notice, the only vowels available on the key are the short vowels अ, इ, उ, ए, ओ (with additional, less used ones like ऋ and ऑ on the corners). This is to utilise the fact that each of these vowels has a corresponding long vowel, and thus there is no need to clutter the key with these. Instead, we provide the key **अ↔आ** which converts short vowels to long vowels and vice versa. This also works on their matras (diacritics).

For example, क + इ = कि, and pressing **अ↔आ** makes it की.

Speaking of diacritics, all the vowels have the corresponding diacritics as their output when a consonant is found as the previous character (except अ, which outputs the ा diacritic, as each consonant has the अ sound by default and ा is probably one of the most frequently used matras). The keyboard has rules in place to dictate what should happen in different scenarios. A few of these include:
- If a *consonant* is found before adding a vowel, the vowel's diacritic is added. For example, क + इ = कि.
- If a *vowel* is found before adding a vowel, the whole vowel is placed, no diacritic (as it is nonsensical to do so). For example, इ + उ = इउ, not इु.
- If a *vowel diacritic* is found before adding a vowel, the whole new vowel is placed. For example, कि + उ = किउ.
- If an *anusvara* (ं), *chandrabindu* (ँ) or *visarga* (ः) is found before adding a vowel, the whole new vowel is placed. For example, कं + उ = कंउ.

#### Matra to Svara Key (े↔ए)
Sometimes, it is not desired to put a matra right after a consonant, but rather a full vowel. This is where the **े↔ए** key comes in. It converts the matra to a full vowel and vice versa. For example, क + े = के, and pressing **े↔ए** makes it कए.

An example of a word I can imagine this would be real helpful for is कई (many), where the ई is a full vowel and not a matra.

### Halant (्)
The halant is a special character in Devanagari that is used to remove the inherent vowel sound from a consonant. It is used to create conjuncts, and is also used in many other scenarios. The halant key is placed at the bottom of the keyboard. Similar to the 12-kana keyboard, it also contains the flick-keys for parentheses, the Devanagari abbreviation sign (॰), and a dash.

### Bindus and nuqtas
The tenth key in the keyboard contains the bindu (ँ), chandrabindu (ं), visarga (ः), chandra (ॅ) and nuqta (़) characters. The keyboard automatically handles the placement of these characters when a vowel is added after them.

A particular note for nuqtas, the order utilised (as with other parts of the keyboard) is consonant + nuqta + matra. Even if you add a matra first, the nuqta will be placed after the consonant. This is to ensure that the nuqta is always placed after the consonant, as is the norm in Devanagari.

## Background - What's the need? Don't we already have keyboards for Devanagari like INSCRIPT or transliteration keyboards?
It has been almost 30 years since the internet was introduced to Indian users. Yet the amount of content on the internet in Indian languages *in their scripts* is near negligible. A major reason for this, in my opinion and probably others who have worked on the topic, is that Indians have never really been provided a consistent input method for their languages, neither has it evolved that well over the decades.
INSCRIPT is a keyboard layout that is standardised by the Government of India, and is available on all major operating systems. While it has its merits in trying to separate the consonants from the vowels while having a layout that is common across Indian languages, it is cumbersome to learn, has too many keys, and is just not (in my opinion) intuitive to a new user. (Another gripe I have with it, especially on desktop, is that it overlays common punctuation marks like "?" making it virtually unusable for modern day-to-day texting, but that's a story for another time :D)

Transliteration keyboards, while good (I personally used them before I made Barakunji), are not perfect. The phonetic predicition text is not always what you are looking for (e.g. हाँ becoming हां on GBoard frequently), and things like ITRANS (to me at least) look very confusing on a mobile device once the underlying QWERTY it's based on is removed. They also require a decently good understanding of English and the Latin alphabet, which is not always the case in India where less than 150 million out of 1.5 billion people speak any bit of the language. (according to Census 2011, might have increased but point still stands)

While I have little to no hope of mainstream online adoption and preservation of the Hindi language in Devanagari from India's urban population, I remain hopeful that more people across the country be able to access and contribute to the internet in their own languages, and that this can be a step forward in the right direction to enabling that.

