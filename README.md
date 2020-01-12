# INSTRUCTIONS FOR RUNNING AND TESTING THE CODE

To Download the posts from reddit I decided to use the PRAW library.

The following are necessary documentation for this use:

**Documentation**:
https://praw.readthedocs.io/en/latest/getting_started/quick_start.html

**reddit username**: reddit_bert_user

**client id**: "Z_U0Fc057pEKJA"
**client secret**: "gDcrvRJaOI8mG97lMLkBehQT_qw"

**user agent**: "local_python:com.task.mysubredditanalysis (by u/reddit_bert_user)"


## INSTRUCTIONS FOR THE JUPITER NOTEBOOK "Imprint_Task.ipynb"

You may run the whole notebook in one go. It should pip install the 3 necessary packages that are not common to all python environments. 

Under the **Constants** Header you will find the client information from Reddit as well as the default N_POSTS=100 as requested and the list of 10 subreddits under the SUBREDDIT_LIST variable.

To get a pandas dataframe of all the subreddit data simply run all the functions before the **Download All the Data** header and then run the first cell that creates new_df.

The following cells simply label encode and split the data.

Under **Task 2 - Classification Model** you must run the first cell which preprocesses the data for the BERT model and then the cells under "Create and fit the BERT Model" will do exactly that.

Under **Evaluate BERT model** the cell evaluates the model with the test data and we obtain a standard report and a confusion matrix.

Under **Create and save predictor to be Served** the first cell creates the predictor from the model and the next cell saves it to the drive for use later.
you can use the "predictor" function directly with predictor.predict("insert text here") to predict the subreddit of any string.

Under **Task 3 - Model Serving** We have a cell with the final function, model_to_serve" that takes as input any string and returns the predicted subreddit it belongs to.
You may test this function with any string/text to get the subreddit prediction.


## SERVING THE MODEL (with Flask)

To serve the model you must run the last cell in the "Imprint_Task.ipynb" notebook (after running the rest of the notebook) and then copy the URL that is produced in the output cell and open the second jupyter notebook "test_flask_app.ipynb" and paste it under the "my_ngrok_url" variable. Then run the whole notebook for each test.


