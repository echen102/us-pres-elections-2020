# 2020 US Presidential Election Tweet IDs

The repository contains an ongoing collection of tweets IDs associated with the 2020 United States presidential elections, with our data collection starting on May 20, 2019. We leveraged Twitter’s streaming API to follow specified accounts and also collect in real-time tweets that mention specific keywords. To comply with Twitter’s [Terms of Service](https://developer.twitter.com/en/developer-terms/agreement-and-policy), we are only publicly releasing the Tweet IDs of the collected Tweets. The data is released for non-commercial research use. We currently have a backlog of historical twitter files that we are working on pre-processing and extracting Tweet IDs from; **we will be releasing both past and future data sets as the data becomes available and as we finish pre-processing the data. Thank you for your patience!**


The associated paper to this repository can be found here: [#Election2020: The First Public Twitter Dataset on the 2020 US Presidential Election](https://arxiv.org/abs/2010.00600)


## Data Organization
The Tweet-IDs are organized as follows:
* Tweet-ID files are stored in folders that indicate the year and month of the collection (YEAR-MONTH). 
* Individual Tweet-ID files contain a collection of Tweet IDs, and the file names all follow the same structure, with a prefix "us-presidential-tweet-id-” followed by the YEAR-MONTH-DATE-HOUR. 
* Note that Twitter returns Tweets in UTC, and thus all Tweet ID folders and file names are all in UTC as well. 

## Notes About the Data


### Other Notes
* We will be continuously maintaining this database for the foreseeable future, and will be uploading new data on a weekly basis.  
* There may be a few hours of missing data due to technical difficulties. We will do our best to recover as many Tweets from those time frames by using Twitter’s search API. 
* We will keep a running summary of basic statistics as we upload data in each new release. 
* The file keywords.txt and accounts.txt contains the updated keywords and accounts respectively that we tracked in our data collection. Each keyword and account will be followed by the date we began tracking them, and date we removed them (if the keyword or account has been removed) from our tracking list. If a keyword or account was added, removed and then re-added, the first date will indicate when the keyword or account was first added to our list, the second date indicates when the keyword or account was removed and the third date is the date that it was subsequently re-added. 
* Consider using tools such as the [Hydrator](https://github.com/DocNow/hydrator) and [Twarc](https://github.com/DocNow/twarc) to rehydrate the Tweet IDs. Instructions for both are in the next section. 
* Hydrating may take a while, and Tweets may have been deleted since our initial collection. If that is the case, unfortunately you will not be able to get the deleted Tweets from querying Twitter's API. 
* The structures and utilties of this dataset repository are based off of our publicly released [COVID-19 Tweet ID dataset collection](https://github.com/echen102/COVID-19-TweetIDs). 

## How to Hydrate

### Hydrating using [Hydrator](https://github.com/DocNow/hydrator) (GUI)
Navigate to the [Hydrator github repository](https://github.com/DocNow/hydrator) and follow the instructions for installation in their README. As there are a lot of separate Tweet ID files in this repository, it might be advisable to first merge files from timeframes of interest into a larger file before hydrating the Tweets through the GUI. 

### Hydrating using [Twarc](https://github.com/DocNow/twarc) (CLI)
Many thanks to Ed Summers ([edsu](https://github.com/edsu)) and Github user [SamSamhuns](https://github.com/SamSamhuns) for writing this script that uses [Twarc](https://github.com/DocNow/twarc) to hydrate all Tweet-IDs stored in their corresponding folders. 

First install Twarc and tqdm
```
pip3 install twarc
pip3 install tqdm
```

Configure Twarc with your Twitter API tokens (note you must [apply](https://developer.twitter.com/en/apply-for-access) for a Twitter developer account first in order to obtain the needed tokens). You can also configure the API tokens in the script, if unable to configure through CLI. 
```
twarc configure
```

Run the script. The hydrated Tweets will be stored in the same folder as the Tweet-ID file, and is saved as a compressed jsonl file
```
python3 hydrate.py
```

# Data Usage Agreement
This dataset is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International Public License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)). By using this dataset, you agree to abide by the stipulations in the license, remain in compliance with Twitter’s [Terms of Service](https://developer.twitter.com/en/developer-terms/agreement-and-policy), and cite the following manuscript: 

Emily Chen, Ashok Deb, Emilio Ferrara. #Election2020: The First Public Twitter Dataset on the 2020 US Presidential Election. Arxiv (2020)

PDF of paper can be found here: [#Election2020: The First Public Twitter Dataset on the 2020 US Presidential Election](https://arxiv.org/abs/2010.00600)

# Statistics Summary (v1.1) 
Number of Tweets : **386,931,793**


# Known Gaps
| Date          | Time               |
|-------------  |-----               |
| 6/16/20       | 17:00 - 24:00 UTC  |
| 6/17/20       | 00:00 - 02:00 UTC  |
| 6/19/20       | 16:00 - 17:00 UTC  |

# Inquiries

Please read through the README and the closed issues to see if your question has already been addressed first. 

If you have technical questions about the data collection, please contact Emily Chen at **echen920[at]usc[dot]edu**.

If you have any further questions about this dataset please contact Dr. Emilio Ferrara at **emiliofe[at]usc[dot]edu**.

# Related Papers
- [Tracking Social Media Discourse About the COVID-19 Pandemic: Development of a Public Coronavirus Twitter Data Set](https://publichealth.jmir.org/2020/2/e19273/) [Datatset Github](https://github.com/echen102/COVID-19-TweetIDs)
- [What types of COVID-19 conspiracies are populated by Twitter bots?](https://firstmonday.org/ojs/index.php/fm/article/view/10633/9548)
- [Political polarization drives online conversations about COVID‐19 in the United States](https://onlinelibrary.wiley.com/doi/full/10.1002/hbe2.202)

