# Data for URI assignment

(see [github.com/OpenITI/2022_1_URI_assignment](https://github.com/OpenITI/2022_1_URI_assignment))

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

Use the identification script https://github.com/OpenITI/2022_1_URI_assignment/identify.py

This script will automatically fill in URIs that have been assigned before.

For texts that have not been identified before, it will try to identify the book
with a URI that is already in the corpus, using the metadata.

* use `git pull` to update your local clone of https://github.com/OpenITI/2022_1_URI_assignment with new URIs identified by other users
* Choose a URI of a book you're interested in from the "URIs_TFIDF" tab in 
  [this spreadsheet](https://docs.google.com/spreadsheets/d/1KamnLCDhqJijznhvgZ3avi1YZb9fJXVO4l-DF2JzUHk/edit?usp=sharing)
* Add your initials to the "Kitabi" column to show you are working on it
* Copy the link to the tsv file
* run the `identify.py` script and provide the link to the tsv file; the script will download the tsv file into the input_data folder in the 2022_1_URI_assignment repo, if it is not there already.
* After going through 20 rows, the script will urge you to upload your identifications to GitHub; simply copy and paste the code the script will provide you into Git Bash.  
* Add the row numbers of the rows you have worked on (e.g.,"1-34") in the "Identified rows" column 
  in the "URIs_TFIDF" tab in [this spreadsheet](https://docs.google.com/spreadsheets/d/1KamnLCDhqJijznhvgZ3avi1YZb9fJXVO4l-DF2JzUHk/edit?usp=sharing)
