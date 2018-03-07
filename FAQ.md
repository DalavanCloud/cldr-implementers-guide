[CLDR](http://cldr.unicode.org) : Implementer’s FAQ
===

To update this document, see [Contributing](#contributing). Note that a mirror of this document is kept on http://cldr.unicode.org/implementers-faq

### ​Q. Why has CLDR lowercased and dropped the hyphen from the ISO-3166-2 codes, e.g. “AD-02” becomes “ad02”

It was done because the identifiers have to be used in a BCP47 context, which puts limitations on the format of identifiers.

### Q.  Why have the subdivisions of France that are separate countries been removed (e.g. Martinique, Reunion, etc.)

The subdivisions occur in a few places in the XML data:

  1. [a complete list with status (validity/subdivision.xml)](http://www.unicode.org/repos/cldr/trunk/common/validity/subdivision.xml)
  1. [the hierarchy (from ISO) (supplemental/subdivisions.xml)](http://www.unicode.org/repos/cldr/trunk/common/supplemental/subdivisions.xml) and [Charts](http://www.unicode.org/cldr/charts/latest/supplemental/territory_subdivisions.html)
  1. [aliases](http://www.unicode.org/cldr/charts/latest/supplemental/aliases.html) and [charts](http://www.unicode.org/cldr/charts/latest/subdivisionNames/index.html)
  1. [translations (common/subdivisions/)](http://www.unicode.org/repos/cldr/trunk/common/subdivisions/)

The code for Martinique is in #2: [`MQ`](http://www.unicode.org/cldr/charts/latest/supplemental/territory_subdivisions.html#frmq) and in [validity/subdivision.xml](http://www.unicode.org/repos/cldr/trunk/common/validity/subdivision.xml), but we generally don't translate if there is an equivalent country code.

### Q. What are the codes for subdivisions based on?

The set of codes is from ISO, but stabilized. That means that we retain codes that ISO has dropped, but mark them as deprecated. This provides a stable set of codes for developers. The complete list is in [validity/subdivision.xml](http://www.unicode.org/repos/cldr/trunk/common/validity/subdivision.xml), and the aliases (with a mapping from older to newer codes) is in [Aliases](http://www.unicode.org/cldr/charts/latest/supplemental/aliases.html)

### Q. Where are the subdivision translations from?

We don't do translations for these in in the survey tool because of the volume, and because it has been lesser priority.

The English has been reviewed, as have the names for England, Scotland, and Wales in main CLDR languages (the last three because of emoji 😀). The rest has been extracted from Wikidata. That Wikidata data is draft, because it is (a) incomplete, and (b) not reviewed. Some simple algorithmic filtering was done, and anything suspect was omitted. When data is imported from Wikidata, existing data is not replaced, so any fixes are retained. 

-----

## Contributing

See an issue? Want to contribute? Please open a pull request at https://github.com/unicode-org/cldr-implementers-guide (You will be asked to sign the CLA when the PR is open, which is one-click with Github)

This document is part of the [CLDR Implementer’s Guide](README.md), and a copy is kept on [http://cldr.unicode.org/implementers-faq](http://cldr.unicode.org/implementers-faq)


## License

See [LICENSE](LICENSE)
