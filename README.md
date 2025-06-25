# A browsable list of datasets and their terms of use

This is preliminary. Basic structure:

- a page for each topic (terms of use, DOI, citations, ...). We'll start with terms of use.
- a CSV file with 3-4 columns that contains the actual information

## Updating

- Create a pull request to modify the CSV file. 
- Add the person updating the information, and the date.
- If the information becomes obsolete, do not delete the entry; rather add a date in the filed `Obsolete`, and create the pull request.
- Additional information can be captured in a file `_information/<NAME>.md`, which should then be referenced in the CSV file (without the `.md` extension, in correct case).


## Technical

The pages are rendered using the [standard Jekyll mechanism](https://jekyllrb.com/tutorials/csv-to-table/), generating a generic [DataTables](https://datatables.net/) table to allow for efficient search.

See discussion [here](https://talk.jekyllrb.com/t/how-to-pull-csv-into-datatables/4936/16).

Sample: see [TermsOfUse.md](TermsOfUse.md).
