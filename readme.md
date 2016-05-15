TextformatterCurrency
=====================

A locale-aware currency formatter module for Processwire.

The module reads a conforming input money formatted string, splits it and formats each valid monetary amount according
to the locale defined in the module settings. The module is capabale of using the visiting browser's headers to
determine which locale to use when formatting monetary amounts of various currencies.


Input money format
------------------

The input money format is made up of any number of currency-amount pairs.

Each input money pair is made up of a currency code and an amount. These are always separated by at least one space with the code coming
first. (eg. ```GBP 50.99``` or ```JPY 100000```.)

- No thousands separators are allowed in the input.
- A full-stop __.__ character is the only acceptable decimal separator.

Each money pair is separated by a configurable character string ('|' by default.) You can change the character used to
split the incoming string into currency-amount pairs in the module settings page.


Output format
-------------

Each currency-amount pair is formatted using the defined locale or that supplied by the browser and thus appears
localised in the output of the formatter. If the input text has more than one currency-amount money pair then the output
will join the localised outputs for each pair using the output glue string defined in the module settings.


Examples Using Module Defaults
------------------------------

Input ```GBP 50.99 | EUR 100``` gives ```£50.99 + €100.00``` when viewed in browser set to British English.
Input ```GBP 50.99 | EUR 100``` gives ```50,99 £GB + 100,00 €``` using browser set to French.

