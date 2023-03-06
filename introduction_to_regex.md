# [Introduction to RegEx](https://launchschool.com/books/regex)

### [Other resources](https://launchschool.com/books/regex/read/preparations#resources)

- [RegexDocs](https://ruby-doc.org/3.2.1/Regexp.html)
- [Rubular](http://rubular.com/)

## [Basic Matching](https://launchschool.com/books/regex/read/basic_matching)

### [Alphanumerics](https://launchschool.com/books/regex/read/basic_matching#alpha-numeric) 

## [Character classes](https://launchschool.com/books/regex/read/character_classes)
## [Range of characters](https://launchschool.com/books/regex/read/character_classes#range)
## [Character Class Shortcut](https://launchschool.com/books/regex/read/class_shortcuts)
## [Anchors](https://launchschool.com/books/regex/read/anchors)
## [Quantifiers](https://launchschool.com/books/regex/read/quantifiers)
### [Greediness](https://launchschool.com/books/regex/read/quantifiers#greediness)

| link | Regex |
| :---: | --- |
| [alphanumeric](https://launchschool.com/books/regex/read/basic_matching#alpha-numeric) | `/c/` |
| [meta-chars](https://launchschool.com/books/regex/read/basic_matching#special) | `$ ^ * + ? . ( ) [ ] { } | \ / / ` |
| [concatenation](https://launchschool.com/books/regex/read/basic_matching#concatenation) | `/cat/` |
| [alternation](https://launchschool.com/books/regex/read/basic_matching#alternation) | `/(cat\|dog\|rabbit)/` |
| [control character escapes](https://launchschool.com/books/regex/read/basic_matching#control) | `\n, \r, and \t` |
| [case](https://launchschool.com/books/regex/read/basic_matching#case) | `/launch/i` |
| [ignoring case](https://launchschool.com/books/regex/read/character_classes#charset) | `/[abAB]/` OR `/[abc][12]/`|
| [ranges](https://launchschool.com/books/regex/read/character_classes#range) | `char.match(/[0-9A-Fa-f]/)` |
| [negated classes](https://launchschool.com/books/regex/read/character_classes#negated) | `/[^aeiou]/` |
| [Any char](https://launchschool.com/books/regex/read/class_shortcuts#dot) | `/./` |
| [whitespace](https://launchschool.com/books/regex/read/class_shortcuts#whitespace) | `/\s/` |
| [digits/hex-digits](https://launchschool.com/books/regex/read/class_shortcuts#digits) | `/\d/` / `/\h/` |
| [word chars](https://launchschool.com/books/regex/read/class_shortcuts#words) | `/\w/` |
| [start/end](https://launchschool.com/books/regex/read/anchors#line-anchors) | `^` and `$ |
| [lines v strings](https://launchschool.com/books/regex/read/anchors#lines-vs-strings) | `TEXT2.match(/fish$/)` |
| [start/end of string](https://launchschool.com/books/regex/read/anchors#string-anchors) | `\A` and `\z` (`\Z` is subtley different)|
| [word boundaries](https://launchschool.com/books/regex/read/anchors#word-bounds) | `\b` |
| [0 or more](https://launchschool.com/books/regex/read/quantifiers#zero-or-more) | `*` |
| [1 or more](https://launchschool.com/books/regex/read/quantifiers#one-or-more) | `+` |
| [0 or 1](https://launchschool.com/books/regex/read/quantifiers#zero-or-one) | `?` |
| [ranges](https://launchschool.com/books/regex/read/quantifiers#ranges) | `/\b\d{10}\b/` or `/\b\d{3,}\b/` or `/\b[a-z]{5,8}\b/i` |
| [lazy matches](https://launchschool.com/books/regex/read/quantifiers#greediness) | ` /a[abc]*?c/` |
