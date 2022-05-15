# CS 232 Final - Latin Classification Model  
  
  
### Folder Descriptions
**ckpt**
This folder contains checkpoints for the classification model.

**data**
This folder contains 3 subfolders: "history", "myth", and "nero." Each subfolder contains textfiles of Latin text that correspond to the genre of the folder title. Each subfolder also includes a "clean.txt" file which contains all the cleaned latin text in the respective subfolder.

**history-dfs**
This folder contains csv files that represent dataframes outputted by "format-data.ipynb". Each dataframe consists of rows that include a Latin sentence, an indication that it is from a historical text, and the sentence's LatinBERT representation. The dataframe is formatted so it can be used as input to the classification model.

**latin-bert-master**
This folder contains the data/code necessary to running Latin BERT (found at https://github.com/dbamman/latin-bert). Its specifics are outlined in its README and the paper "Latin BERT: A Contextual Language Model for Classical Philology" (https://arxiv.org/abs/2009.10053).

**myth-dfs**
This folder contains csv files that represent dataframes outputted by "format-data.ipynb". Each dataframe consists of rows that include a Latin sentence, an indication that it is from a mythical text, and the sentence's LatinBERT representation. The dataframe is formatted so it can be used as input to the classification model.

**myth-dfs**
This folder contains csv files that represent dataframes outputted by "format-data.ipynb". Each dataframe consists of rows that include a Latin sentence and the sentence's LatinBERT representation. The dataframe is formatted so it can be used as input to the classification model.
  
  
### File Descriptions
**clean_data.ipynb**
This notebook removes numbers, punctuation (since punctuation doesn't exist in Latin), and any nonwords from the raw Latin textfiles found in the data folder. It outputs the cleaned text to a textfile called "clean.txt" in the respective data subfolder of its genre. For example, the textfile "data/history/caesar.txt" would be cleaned then added to the file "data/history/clean.txt"

**format-data.ipynb**
This notebook splits the cleaned data (ie the three "clean.txt" files) into chunks of 10 words. It then uses LatinBERT to extract the sentence representation of each chunk and saves these features along with its classification in a dataframe that gets outputted to a csv file. The csv is formatted so the model can take data as input.

**get_livy.ipynb**
This notebook gets the Livy data from http://www.thelatinlibrary.com/livy/liv.1.shtml and outputs the Latin text into a textfile.

**get_ovid.ipynb**
This notebook gets the Ovid data from https://www.thelatinlibrary.com/ovid.html and outputs the Latin text into a textfile.
It is also used for Aeneid and other Latin Library texts:
https://www.thelatinlibrary.com/verg.html
https://www.thelatinlibrary.com/apuleius/apuleius.shtml

**nero_model.ipynb**
This notebook loads the model trained in train_model.ipynb and classifies the primary Latin text sources on Nero. It also outputs some visualizations reguarding its classification. 

**train_model.ipynb**
This notebook builds and trains a classification model that determines if a Latin sentence is historical or mythological.  


### How to run code
The train_model.ipynb notebook creates the classification model using the dataframes outputted by format-data.ipynb. The nero_model.ipynb notebook uses this model to classify novel data.