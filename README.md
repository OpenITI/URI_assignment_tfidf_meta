# Data for URI assignment

(see [github.com/OpenITI/2022_URI_session](github.com/OpenITI/2022_URI_session))

The data is organized by book URI. For each book URI, there is a tsv file 
that contains metadata for all files from new collections that have a tf-idf score of
more than 25% for any of the versions of this book in the corpus.

The idea is that it's easier, and more interesting, to identify books that are close to books you are familiar with.

Each row in such a tsv file contains information on one book from the new collections. 

Each tsv file contains the following columns: 

* automatic URI	: automatically assigned URI (usually empty)
* Proposed URI: previously manually proposed URI (usually empty)
* bookTitle: book title of the new file (from collection's metadata)
* authorName: author's name (from collection's metadata)
* collection: name of the collection
* id: id of the book within the collection
* tfidf: highest tf-idf score of this book to any version of the tsv file's URI


## How to use these files?

### first option: use the identification script github.com/OpenITI/2022_URI_session/identify.py

This script will automatically fill in URIs that have been assigned before.

For texts that have not been identified before, it will try to identify the book
with a URI that is already in the corpus, using the metadata.

* use `git pull` to update your local clone of github.com/OpenITI/2022_URI_session with new URIs identified by other users
* Choose a URI of a book you're interested in from the "URIs_TFIDF" tab in 
  [this spreadsheet](https://docs.google.com/spreadsheets/d/1KamnLCDhqJijznhvgZ3avi1YZb9fJXVO4l-DF2JzUHk/edit?usp=sharing)
  and add your initials to the "Kitabi" column to show you are working on it
* Download the tsv file of that URI (link in the second column of the spreadsheet) and save it to the `input_data` folder of your local clone of github.com/OpenITI/2022_URI_session (**IMPORTANT: make sure the file is saved with the extension ".tsv", not ".txt"**)
* run the `identify.py` script and provide the filename of the tsv you downloaded when asked for it 
* After you finished identifying files, use `git add`, `git commit`, `git pull` and `git push` 
  to synchronize your local clone and the repo on GitHub 
* Add the row numbers of the rows you have worked on (e.g.,"1-34") in the "Identified rows" column 
  in the "URIs_TFIDF" tab in [this spreadsheet](https://docs.google.com/spreadsheets/d/1KamnLCDhqJijznhvgZ3avi1YZb9fJXVO4l-DF2JzUHk/edit?usp=sharing)


### Alternatively: in spreadsheet

* Choose a URI of a book you're interested in from the "URIs_TFIDF" tab in 
  [this spreadsheet](https://docs.google.com/spreadsheets/d/1KamnLCDhqJijznhvgZ3avi1YZb9fJXVO4l-DF2JzUHk/edit?usp=sharing)
  and add your initials to the "Kitabi" column to show you are working on it
* Download the tsv file of that URI (link in the second column of the spreadsheet) and save it to the `input_data` folder of your local clone of github.com/OpenITI/2022_URI_session (**IMPORTANT: make sure the file is saved with the extension ".tsv", not ".txt"**)
* Load the tsv file into a spreadsheet program
* add a column at the beginning of the file and name it "manually_added_URI"
* Go through the spreadsheet and write URIs in that new column
* Remove all rows below the last row you have identified
* save the file as a tsv file in the output folder of the github.com/OpenITI/2022_URI_session repo
* use `git add`, `git commit`, `git pull` and `git push` to synchronize your local clone and the repo on GitHub 
* Add the row numbers of the rows you have worked on (e.g.,"1-34") in the "Identified rows" column 
  in the "URIs_TFIDF" tab in [this spreadsheet](https://docs.google.com/spreadsheets/d/1KamnLCDhqJijznhvgZ3avi1YZb9fJXVO4l-DF2JzUHk/edit?usp=sharing)
