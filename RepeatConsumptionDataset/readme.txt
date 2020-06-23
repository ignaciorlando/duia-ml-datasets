
This dataset contains user consumption data, in the form of sparse matrices (User x Items), the values of which are how many times user u consumed item i.

========================================================================
Citation.
========================================================================
This directory contains the count data used in the paper Predicting Consumption Patterns with Repeated and Novel Events by Kotzias et al..
If you use this dataset, please make sure to cite the paper.
The code for the paper can be found here: https://github.com/UCIDataLab/repeat-consumption



========================================================================
Structure
========================================================================
This directory contains 7 subdirectories corresponding to data from twitter (2), gowalla (2), lastfm (1) and reddit (2). For details about how and when these datasets were collected, please read
the paper. 

In every directory there are 3 files, one for training, one for validation and one for testing. Each .csv file contains a User x Item sparse matrix in COO form.
COO form, means that each line contains a (row, column, value) triplet for the non zero entries. More here https://docs.scipy.org/doc/scipy/reference/generated/scipy.sparse.coo_matrix.html 

There is code that can construct any of these with numpy here : https://github.com/UCIDataLab/repeat_consumption/blob/master/util/io.py (load array)

The files are in .csv format so they can be read in other programming languages as well.



========================================================================
Details
========================================================================
Each matrix contains how many times a user 'consumed' and item. Items can be locations, artists, or subreddits. 
Details about each dataset are presented below. (In the parenthesis is the number of Users x Items)

tw_oc (13k x 11k): tweets with geolocation from Orange County CA area. Items are locations a user visits in this case.
tw_ny (30k x 11k): Same as tw_oc but from the New York area.

go_sf (2k x 7k): Check-ins from the app Gowalla, from the San Fransisco area. Full dataset here: https://snap.stanford.edu/data/loc-gowalla.html
go_ny (1k x 7k): Same as go_sf, but from the New York area.

lastfm (992 x 15k): How many times, a user listened to each artist. Covers 3 years of listening habbits, full dataset here: http://www.dtic.upf.edu/∼ocelma/MusicRecommendationDataset/lastfm-1K.html

reddit_top (113k x 21k): How many times a user posted in a subreddit. These are the 130k most active users from 2015 and 20k most subscribed subreddits. This dataset is very large and can take a lot of time to load/use.
reddit_sample (20k x 21k): Same as reddit_top, but a sample of 20k users.
