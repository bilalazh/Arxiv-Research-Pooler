## Arxiv Research Pooler
**How to run this code**

Click on `Open In Colab` Button , doing that should take you to Colab Notebook

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bilalazh/Arxiv-Research-Pooler/blob/main/Arxiv_Research_pooler.ipynb)

or 

just `git clone https://github.com/bilalazh/Arxiv-Research-Pooler.git`in your terminal and place the `.ipynb` any where in your Google Drive to access it 


#### Objectives and Motivations for this Repo 

- Sheer volume of Academic Paper published on platforms like ArXiv can be overwhelming 
There were 7716 papers published  only in first 12 days of October 2023 [This number is taken from this link here](https://arxiv.org/stats/monthly_submissions)


- It can take hours to find relevant papers and not to mention downloading them and renaming all the `2310.07709.pdf` files  can take so much time 

- Literature Review process is very time consuming and harder then it should be 

##### How this Notebook can help :

- This notebook solves this problem -> you enter a _title_  and it finds papers with relevant keywords  and render them nicely in _markdown format_ 

- You can Bulk download papers with proper titles and then save them locally as `.zip` file



**Parts of code**

_**Script for Parsing and displaying titles and summaries**_

1. **Imports**: The script begins by importing the necessary libraries. These libraries include `feedparser`, `urllib.parse`, `textwrap`, `time`, `IPython.core.display`, `datetime`, and `re`. 

2. The `extract_arxiv_id` function is defined. This function extracts the arXiv ID from a given link.

3. **User Input**: The script prompts the user to enter a search keyword. This keyword is used to construct the search query for the arXiv API. The user's input is crucial as it determines the scope of the search.

4. **API Request**: The script forms a complete URL for the request using the base URL for the arXiv API and the parameters dictionary. It then makes a GET request to the API and parses the response.

5. **Response Parsing and Display**: If the response contains entries, the script parses the response and loops over the entries. For each entry, it extracts and displays detailed information such as the `title`, `summary`, `URL`, `authors`, `published date`, `updated date` `arXiv ID`, and `Primary category`. The output is displayed in Markdown format for easy readability.


_**Bulk Downloading Articles In Colab**_

1. **Using arxiv-dl** : This command line tool is already installed when you run the first cell

2. **Usage** : You can just enter `Arxiv Id ` from the markdown outout and paste it after `!paper` like this  `!paper  2306.16623v1`
 This will download the paper and rename it like this ->

 ```
 [Done] Paper saved to "/content/arxiv-paper/2306.16623v1_The_Segment_Anything_Model_SAM_for_Remote_Sensing_Applications_From_Zero_to_One_Shot.pdf"
 ```
3. **Downloading Multiple papers with single command**
- you can add more then one id in the command and chain them togather like in this example
```
!paper  id 1 id 2  .. -d /location/dir/
```
like this
```
!paper `2302.24532v1` `2342.3532v2` -d /content/arxiv paper
```
to download more then one paper at the directory `arxiv-paper`

_**Zipping files and Downloading to Local storage**_

1. Run this cell to download the contents of `arxiv-paper` folder as zip files 
you can modify the name of the zip file as well

```
!zip -r arxiv-paper.zip arxiv-paper
```

2. **Download the zip file**

 run this cell
 ```
 from google.colab import files
files.download('arxiv-paper.zip'
```
to download .zip file 




##### Features and Development 
- More features will be addded periodically
- Expect different edits in this notebook or more notebooks added to this repository with more advanced/different features 






*Your Feedback is appreciated*


 Massive thanks to these projects for making this possible:
- [Arxiv .org ](https://arxiv.org/)
- [Feedparser](https://pypi.org/project/feedparser/)
- [arXiv-dl](https://pypi.org/project/arxiv-dl/)

