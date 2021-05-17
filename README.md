# 2020 US Presidential Election Tweet IDs

**We will be stopping regular updates of this repository on June 21, 2021. This dataset aims to capture discourse from the 2020 election cycle, and we will continue to collect and post tweet IDs through 6 months after President Biden's inauguration.**
The repository contains an ongoing collection of tweets IDs associated with the 2020 United States presidential elections, with our data collection starting on May 20, 2019. We leveraged Twitter’s streaming API to follow specified accounts and also collect in real-time tweets that mention specific keywords. To comply with Twitter’s [Terms of Service](https://developer.twitter.com/en/developer-terms/agreement-and-policy), we are only publicly releasing the Tweet IDs of the collected Tweets. The data is released for non-commercial research use. We currently have a backlog of historical twitter files that we are working on pre-processing and extracting Tweet IDs from; **we will be releasing both past and future data sets as the data becomes available and as we finish pre-processing the data. Thank you for your patience!**


The associated paper to this repository can be found here: [#Election2020: The First Public Twitter Dataset on the 2020 US Presidential Election](https://doi.org/10.1007/s42001-021-00117-9)

## Data Organization
The Tweet-IDs are organized as follows:
* Tweet-ID files are stored in folders that indicate the year and month of the collection (YEAR-MONTH). 
* Individual Tweet-ID files contain a collection of Tweet IDs, and the file names all follow the same structure, with a prefix "us-presidential-tweet-id-” followed by the YEAR-MONTH-DATE-HOUR. 
* Note that Twitter returns Tweets in UTC, and thus all Tweet ID folders and file names are all in UTC as well. 

## Notes About the Data


### Other Notes
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

Chen, E., Deb, A. & Ferrara, E. #Election2020: the first public Twitter dataset on the 2020 US Presidential election. J Comput Soc Sc (2021). [https://doi.org/10.1007/s42001-021-00117-9](https://doi.org/10.1007/s42001-021-00117-9)

The published paper can be found [here](https://doi.org/10.1007/s42001-021-00117-9) at the Journal of Computational Social Science. 

PDF of paper can also be found here on arXiv: [#Election2020: The First Public Twitter Dataset on the 2020 US Presidential Election](https://arxiv.org/abs/2010.00600)


# Statistics Summary (v1.28) 
Number of Tweets : **1,536,768,510**

Language breakdown of top 10 most prevalent languages : 
| Language        | ISO     | No. tweets       | % total Tweets     |
|-------------    |-----    |------------      |----------------    |
| English         | en      | 1,359,808,462    | 88.48%             |
| Undefined       | und     | 105,075,184      | 6.84%              |
| Spanish         | es      | 25,496,392       | 1.66%              |
| French          | fr      | 7,712,180        | 0.5%               |
| Portuguese      | pt      | 7,407,532        | 0.48%              |
| Japanese        | ja      | 4,863,153        | 0.32%              |
| Turkish         | tr      | 3,398,421        | 0.22%              |
| German          | de      | 2,369,613        | 0.15%              |
| Indonesian      | in      | 2,138,200        | 0.14%              |
| Italian         | it      | 2,130,598        | 0.14%              |


# Known Gaps
| Date           | Time               |
|-------------   |-----               |
| 12/06/19       | 00:00 - 23:00 UTC  |
| 12/07/19       | 18:00 - 19:00 UTC  |
| 12/07/19       | 18:00 - 19:00 UTC  |
| 12/29/19       | 01:00 - 02:00 UTC  |
| 01/03/20       | 05:00 - 06:00 UTC  |
| 01/05/20       | 02:00 - 24:00 UTC  |
| 01/06/20       | 00:00 - 18:00 UTC  |
| 01/19/20       | 04:00 - 23:00 UTC  |
| 01/25/20       | 01:00 - 20:00 UTC  |
| 01/28/20       | 22:00 - 24:00 UTC  |
| 01/29/20       | 00:00 - 05:00 UTC  |
| 02/02/20       | 03:00 - 18:00 UTC  |
| 02/04/20       | 19:00 - 24:00 UTC  |
| 02/05/20       | 00:00 - 23:00 UTC  |
| 03/05/20       | 23:00 - 24:00 UTC  |
| 03/06/20       | 00:00 - 24:00 UTC  |
| 03/07/20       | 00:00 - 02:00 UTC  |
| 03/09/20       | 19:00 - 22:00 UTC  |
| 03/17/20       | 00:00 - 01:00 UTC  |
| 03/21/20       | 23:00 - 24:00 UTC  |
| 03/25/20       | 22:00 - 24:00 UTC  |
| 03/26/20       | 00:00 - 15:00 UTC  |
| 04/02/20       | 00:00 - 23:00 UTC  |
| 04/12/20       | 00:00 - 15:00 UTC  |
| 04/16/20       | 23:00 - 24:00 UTC  |
| 04/18/20       | 23:00 - 24:00 UTC  |
| 04/19/20       | 00:00 - 05:00 UTC  |
| 04/21/20       | 22:00 - 24:00 UTC  |
| 04/27/20       | 22:00 - 24:00 UTC  |
| 04/28/20       | 01:00 - 14:00 UTC  |
| 04/30/20       | 20:00 - 24:00 UTC  |
| 05/01/20       | 00:00 - 24:00 UTC  |
| 05/02/20       | 00:00 - 04:00 UTC  |
| 05/05/20       | 17:00 - 18:00 UTC  |
| 05/07/20       | 00:00 - 13:00 UTC  |
| 05/17/20       | 23:00 - 24:00 UTC  |
| 05/18/20       | 00:00 - 15:00 UTC  | 
| 05/23/20       | 23:00 - 24:00 UTC  | 
| 05/26/20       | 21:00 - 24:00 UTC  |
| 05/27/20       | 00:00 - 03:00 UTC  |
| 05/30/20       | 16:00 - 24:00 UTC  |
| 05/31/20       | 00:00 - 06:00 UTC  |
| 06/01/20       | 17:00 - 19:00 UTC  |
| 06/03/20       | 18:00 - 22:00 UTC  | 
| 06/04/20       | 21:00 - 24:00 UTC  |
| 06/05/20       | 00:00 - 17:00 UTC  |
| 06/07/20       | 14:00 - 24:00 UTC  |
| 06/08/20       | 00:00 - 04:00 UTC  |
| 06/12/20       | 20:00 - 24:00 UTC  |
| 06/13/20       | 00:00 - 21:00 UTC  |
| 06/16/20       | 17:00 - 24:00 UTC  |
| 06/17/20       | 00:00 - 02:00 UTC  |
| 06/19/20       | 16:00 - 17:00 UTC  |

# Inquiries

Please read through the README and the closed issues to see if your question has already been addressed first. 

If you have technical questions about the data collection, please contact Emily Chen at **echen920[at]usc[dot]edu**.

If you have any further questions about this dataset please contact Dr. Emilio Ferrara at **emiliofe[at]usc[dot]edu**.

# Related Papers
- [Tracking Social Media Discourse About the COVID-19 Pandemic: Development of a Public Coronavirus Twitter Data Set](https://publichealth.jmir.org/2020/2/e19273/) [Datatset Github](https://github.com/echen102/COVID-19-TweetIDs)
- [What types of COVID-19 conspiracies are populated by Twitter bots?](https://firstmonday.org/ojs/index.php/fm/article/view/10633/9548)
- [Political polarization drives online conversations about COVID‐19 in the United States](https://onlinelibrary.wiley.com/doi/full/10.1002/hbe2.202)
- [Characterizing social media manipulation in the 2020 U.S. presidential election](https://firstmonday.org/ojs/index.php/fm/article/view/11431)
- [COVID-19 misinformation and the 2020 U.S. presidential election](https://misinforeview.hks.harvard.edu/article/covid-19-misinformation-and-the-2020-u-s-presidential-election/)

