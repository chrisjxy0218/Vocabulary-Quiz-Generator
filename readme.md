## Web-scraping Vocabulary Quiz Generator
### Introduction
This is a project that aims to change the format of BBA's daily vocabulary quiz, with more emphasis on contextual meaning instead of on Chinese-English translation. 

The way we achieve this is to utilize sample sentences of each word in the GRE book (It could be adjusted in the future to be applied to other books as well). 
The source of those sample sentences is the Merriam-Webster online dictionary. 
This program primarily automates the process searching and documenting sample sentences for all words in the GRE book (around 6000)
, with close to no human effort.

### What's inside the package
The project essentially contains three programs, two of them integrated into one file. 
We also include the outputs of them. The programs are 
* A wordlist generator that takes the `.txt` form of the GRE book and generate a list of words that is in the book.
* A webscraper that takes the words as inputs, requests corresponding webpages, and documents the sample sentences provided on the webpages.
* An automated Word document generator that takes the sample sentences as inputs, and outputs formatted word documents suitable for physical printing.

The first two programs are integrated into the file `webscraper.ipynb`, while the third is in `docgenerator.ipynb`.
Also inside the package are the outputs of the webscraper in `outputs.csv` that could be directly used by `docgenerator.ipynb` to generate a .docx file. 
There are also sample outputs of `docgenerator.ipynb`. One is a .docx file, `trial_full.docx` containing sample sentences of **all** words in the book; 
the other is a folder, `Sample Sentences per List` containing 43 `.docx` files, each containing sample sentences of words within a list in the book


### Procedures
If the sole purpose of the user of this package is to generate physically printable vocabulary quizzes, the user only needs to 
* run `docgenerator.ipynb` 
* provide the start and end of a list of words in the order that they appear in the GRE book, as prompted by the program.

If the user would also like to re-run the web-scraper program for reasons including but not limited to refining it, or learning corresponding knowledge, there are important things to consider:
Because the web-scraper is based on the structure of the webpage, which in itself is subject to constant changes made by its developers, the `webscraper.ipynb` **might not work each time** without modification.
If it does not work, the potential modifications are simple, following the structure of the program. They are explained in the comments in `webscraper.ipynb`.
If it does, no inputs from the user are required.

While running the webscraper, make sure to have good internet connection for at least one hour. The exact execution time may depend on the user's internet conditions.
Should there be errors raised on being limited access to the website, disable the comments  `time.sleep(3)` that provides intermission between consecutive searches. (Note this increases the execution time significantly to around five hours for the GRE book)
