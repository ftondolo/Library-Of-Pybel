# Miniaturized Library Of Pybel
## About
A branch of cakenggt's beatifully integrated Python Library of Babel (https://github.com/cakenggt/Library-Of-Pybel) with the aim of reducing executable size.
## Functionality
### Python Implementation

*Note: Usage description from cakenggt's repository *

Address format: `Hex_Value`:`Wall`:`Shelf`:`Volume`:`Page`

Run the file from the command line with an action argument. The following arguments are supported:
* `--checkout <addr>` Checks out a page of a book. Also displays the page's title.
* `--fcheckout <file>` Does exactly the checkout does, but with address in the file.
* `--search <'text'>` Does 3 searches for the text you input.
  * Page contains: Finds a page which contains the text.
  * Page only contains: Finds a page which only contains that text and nothing else.
  * Title match: Finds a title which is exactly this string. 
  Mind the quotemarks.*For a title match, it will only match the first 25 characters. Addresses returned for title matches will need to have a page number added to the tail end, since they lack this.*
* `--fsearch <file>`  Does exactly the search does, but with text in the file.
* `--file <file>` Dump search result into the file.
* `--help` Prints help message.

## Explanation

Seeking to miniaturize cakenggt's clever text-to-address encoding scheme Python implementation of the Library of Babel to a final script size inferior to 8kb due to storage constraints I turned to pyminifier! (https://github.com/liftoff/pyminifier)

Using bz2 compression on a base64 encoded version of his script final size was reduced to a little over 3316 bytes. Over cmpreession algorithms resulted in smaller final file sizee but also broke functionality, either completely (lzma), or partially (gzip).
