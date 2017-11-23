# Readme

## About

Mya2Rom is a simple script --- Javascript-based at the moment --- that converts Burmese script into various romanisation systems.
At present, it converts it into:
- International Phonetic Alphabet (IPA)
	- namely, the flavour used in Wikipedia. One noticeable feature is the use of 'N' instead of nasalised vowels.
- Myanmar Language Commission Transcription System (MLCTS)
	- an orthographical transcription system, created by the MLC
- MLCTS, modified
	- a more phonetical version of MLCTS
	- this version is used by the MLC itself for their Myanmar-English dictionary, as well as by sites such as SEALang
- Simplified systems (just called _Simple1_ and _Simple2_)
	- they are simplified and eschew tonal marks and does not differentiate
	- these are based on phonetic and orthgraphical transcriptions, respectively
	- **Note:** The simplified systems are still works-in-progress
	
This script began as only Mya2IPA, and is based mainly on the Python script by [Thura Hlaing](https://gist.github.com/trhura),
particularly the Burmese letter and IPA letter equivalences. 

The method used to perform syllable splitting is Wiktionary template's [auto-IPA script](https://en.wiktionary.org/wiki/Module:my-pron).

Extended romanisation tables based on [Wikipedia's <Burmese Alphabet>] article and [Wiktionary's <Burmese transliteration>](https://en.wiktionary.org/wiki/Wiktionary:Burmese_transliteration) page
IPA sound/pronunciation change rules based on abovementioned Wikipedia <Burmese Alphabet> article.

The Wikipedia and Wiktionary resources are under the [Creative Commons Attribution-ShareAlike License](https://en.wikipedia.org/wiki/Wikipedia:Text_of_Creative_Commons_Attribution-ShareAlike_3.0_Unported_License)


## Updates

- 23 Nov 2017
	- Not an update; 0.4.1 is the first GitHub version.

- 12 Jul 2017 (0.4.1):
	- Fixed the oversight of not taking into account the vertical bar enclosed alternatives when performing substitutions  
  
[Older, pre-0.4.1 updates are in _Old Readme.txt_]

## Limitations
- Not a limitation per-se, but standalone consonants are automatically given an inherent letter (နွှ => n̥wa̰)
- It does not convert "stacked" letters
- Asat'ed letters (used in transliterations (Like "t" in Watson)) do not currently convert successfully all the time.
	- Might be treated as part of a syllable final 
- It is a what-you-type-is-what-you-get automated romaniser, which means it does not:
    - take into account schwas
			- Nevertheless, schwas are provided together with the full vowel, as an alternative.
    - take into account voicing sandhi (where unvoiced letters become voiced ones)
	  	- (for example, ရင်းပင် will be jɪ́ɴ pɪ̀ɴ instead of jɪ́ɴ bɪ̀ɴ)
	  - See https://en.wikipedia.org/wiki/Burmese_language#Consonants)
- Unlike for schwas, the alternatives are not provided, to make the results cleaner.
- It does not transcribe correct words derived from Pali or Sanskrit that has special/different pronunciations
	- Eg: ဘုရား "Buddha" would be transcribed as /bṵ.já/ instead of /pʰa.já/, as ordinarily, ဘု is /bṵ/

## Bugs
- A problem detecting ဦး (high-tone ဦ)
- Some problems with words like သင်္ဘော, where ဘော is not transcribed correctly... (probably also because of stacking?)
- Some problems with ယျ, which occurs in မေတ္တေယျဘုရား
	- ယျ becomes /jj-/, which is generally just merged into /j-/
			
## TODO
- [x] Investigate possibility of displaying alternatives as full syllables, instead of using "/" per alt-letter, to make things more readable.
	- this was done in 0.4
- [] LONG TERM: extend to cover other romanisation systems
	- We now have MLCTS and the modified MLCTS("MLCTS2"), but others will be added progressively.
	
- To ensure stacking order for diacritics, or letters are uniform or normalised. 
	- [x] asat and anusvara order
		- asat-aukmyit order will now be normalised to aukmyit-asat order
	- [] usage of ၀ (digit 0) for ဝ (letter /w/)
	- WIKT's auto-romaniser performs this check and normalisation, so we can do something similar.
		- Wait... does it? I was sure it did, but I can't find that part now...