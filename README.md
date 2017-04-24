# Finding Wrong Punctuation Before Publishing

This is a collection of Regular Expressions to be used before publishing a document in order to find wrong punctuation. I recommend using them in the order shown here.

> Be careful! Markdown removes trailing spaces in code, so the “replace with” is sometimes not displayed correctly. I use `·` as a symbol for one space in the replace section.

### No Empty Lines
Search for `\n{2,}`

Replace with `\n`

### No Double Spaces
Search for `[ ]{2,}`

Replace with `·`

### No En-Dash instead of a Hyphen
Search for `([\S])[–]([\S])`

Replace with `$1-$2`

### No Hyphen instead of an En-Dash
Search for `([ ])[-]([ ])`

Replace with `·–·`

### No three periods instead of an ellipse
Search for `[.]{3}`

Replace with `…`

### No wrong apostrophe
Search for `([\w])[']`

Replace with `$1’`

### Space after Punctuation
Search for `[.,!?](?!\d)\w`

Check those by hand, as URLs may be selected as well.

### No multiple Punctuation
Search for `([.,!?]){2,}`

Replace with `$1`

### English Quotation Marks
Search for `(\s)["„”](\w)`

Replace with `$1“$2`

Search for `(\w)["“„](\s)`

Replace with `$1”$2`

Search for `(\s)['‚’](\w)`

Replace with `$1‘$2`

Search for `(\w)['‘‚](\s)`

Replace with `$1’$2`

#### Find English Double Quotation Marks Within Double Quotation Marks
Search for `(?:“[^”]*)(“)`

Replace with `‘`

Search for `(”[^“]*)(?:”)`

Replace with `’`

### German Quotation Marks
Search for `(\s)["”“](\w)`

Replace with `$1„$2`

Search for `(\w)["”„](\s)`

Replace with `$1“$2`

Search for `(\s)['‘’](\w)`

Replace with `$1‚$2`

Search for `(\w)['’‚](\s)`

Replace with `$1‘$2`

#### Find German Double Quotation Marks Within Double Quotation Marks
Search for `(„[^“]*)(„)`

Replace with `$1‚`

Search for `(“[^„]*)(?:“)`

Replace with `‘`
