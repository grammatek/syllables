# Syllables for Icelandic

This module adds syllabification and stress labeling to phonetic transcriptions of Icelandic. You can use it to enrich existing dictionaries, i.e. produce dictionaries with syllable and stress labeling, or as an element in a TTS pipeline, to add those labelings to transcribed input text.

## Data

Regardless of the use case, you have to know your phone set. The module provides necessary data for the SAMPA and IPA phonetic alphabets, if you are using something else you have to create your own `data/cons_clusters_your_alphabet.txt` and `data/vowels_your_alphabet.txt`. All filenames are defined in `src/dictionaries.py`, adjust according to your setup.

## Enrich a dictionary

To produce a pronunciation dictionary, call `syllabify_and_label_dict(your_dictionary)`, where `your_dictionary` is a filename of a pronunciation dictionary in plain text format, one entry per line, word and transcription separated by `\t`, each phone separated by space:

```
aaron	a: r O n
abbadísin	a p a t i s I n
abbas	a p a s
...
```

There are two possible outputs implemented, the syllable structure allows you, however, to easily adapt the output to your needs.

**CMU-format**

```
("aaron" nil (((a: ) 1) ((r O n ) 0)))
("abbadísin" nil (((a ) 1) ((p a ) 0) ((t i ) 1) ((s I n ) 0)))
("abbas" nil (((a ) 1) ((p a s ) 0)))
...
```

**Plain syllable formt (no stress labels)**

```
aaron	a:.r O n
abbadísin	a.p a.t i.s I n
abbas	a.p a s
```



## Trouble shooting & inquiries

This application is still in development. If you encounter any errors, feel free to open an issue inside the
[issue tracker](https://github.com/grammatek/syllables/issues). You can also [contact us](mailto:info@grammatek.com) via email.

## Contributing

You can contribute to this project by forking it, creating a private branch and opening a new [pull request](https://github.com/grammatek/syllables/pulls).  


## License

[![Grammatek](app/assets/images/grammatek-logo-small.png)](https://www.grammatek.com)

Copyright © 2020, 2021 Grammatek ehf.

This software is developed under the auspices of the Icelandic Government 5-Year Language Technology Program, described
[here](https://www.stjornarradid.is/lisalib/getfile.aspx?itemid=56f6368e-54f0-11e7-941a-005056bc530c) and
[here](https://clarin.is/media/uploads/mlt-en.pdf) (English).

This software is licensed under the [Apache License](LICENSE)