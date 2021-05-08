## Lingua 1.2.1 (released on 8 May 2021)

### Improvements

- Language detection for sentences with more than 120 characters now
  performs more quickly by iterating through trigrams only which is
  enough to achieve high detection accuracy.
- Textual input that includes logograms from Chinese, Japanese or Korean
  is now split at each logogram and not only at whitespace. This
  provides for more reliable language detection for sentences that
  include multi-language content.
  
### Bug Fixes

- Errors in the rule engine for the Latvian language have been resolved.
- Corrupted characters in the Latvian test data have been corrected.

## Lingua 1.2.0 (released on 8 Apr 2021)

### Features

- A `LanguageDetector` can now be built with lazy-loading required language models
on demand (default) or with preloading all language models at once by calling
`LanguageDetectorBuilder.with_preloaded_language_models()`. (#10)  

## Lingua 1.1.0 (released on 31 Jan 2021)

### Languages

- The Maori language is now supported.
Thanks to @eekkaiia for the contribution. (#5)

### Performance

- Loading and searching the language models has been quite slow so far.
Using parallel iterators from the [Rayon](https://github.com/rayon-rs/rayon)
library, this process is now at least 50% faster, depending on how many
CPU cores are available. (#8)
  
### Accuracy Reports

- Accuracy reports are now also generated for the [*CLD2*](https://github.com/emk/rust-cld2)
library and included in the language detector comparison plots. (#6)
  
## Lingua 1.0.3 (released on 15 Jan 2021)

### Bug Fixes

- Lingua could not be used within other projects because of a private
serde module that was accidentally tried to be exposed.
Thanks to @luananama for reporting this bug. (#9)  

## Lingua 1.0.2 (released on 22 Nov 2020)

### Bug Fixes

- Accidentally, bug #3 was only partially fixed. This has been corrected.

## Lingua 1.0.1 (released on 22 Nov 2020)

### Bug Fixes

- When trying to create new language models, the `LanguageModelFilesWriter` panicked
when it recognized characters in a text corpus that consist of multiple bytes.
Thanks to @eekkaiia for reporting this bug. (#3)

## Lingua 1.0.0 (released on 21 Nov 2020)

This is the very first release of Lingua for Rust. 
Took me 5 months of hard work in my free time. 
Hope you find it useful. :)