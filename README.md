# Consumer_Complaints
This is a repo for Insight Data Engineering - Coding Challenge - Consmer Complaints

### 0. Before we dig into this challenge...
My laptop is Microsoft Laptop2, but I am using Python 3.7 in the Ubuntu Subsystem to create my program and then utilize pyinstaller to convert it into an executable file. 

I uploaded my github repo at this [page](https://insight-cc-submission.com/test-my-repo-link). There is an error relevant to system generating the file.

```Errors exist: Your run.sh file has hidden characters that must be removed first. This is often due to files being created on a Windows machine and having hidden carriage returns instead of newlines.```

So, I tried some ways (dos2unix, sed) following the instruction [here](https://www.networkworld.com/article/3438857/how-to-remove-carriage-returns-from-text-files-on-linux.html) to fix this error, but no luck. Then, I went to see if Notepad++ and Sublime can help me. I can change the line ending from Windows '\r\n' to Unix '\n' in both softwares, but the modified `run.sh` still don't pass your online test system.:-(


### 1. Question Analysis
There are **three main** tasks to solve.
1. total number of complaints received for that product and year. 
2. total number of companies receiving at least one complaint for that product and year. 
3. highest percentage (rounded to the nearest whole number) of total complaints filed against one company for that product and year.

After taking a look of the example `input.csv`, three colomns of information are important for these tasks:
1. Date received (Year)
2. Product
3. Company

----
### 2. Approach
In my codes, I take use of two [Python built-in modules (csv and datatime)](https://docs.python.org/3/py-modindex.html) and two basic [data structures (list and dictionary)](https://docs.python.org/3/tutorial/datastructures.html).

The first step is to acquire *year*, *product* and *company* of eah row, as well as assemble these info into a list named *Case*.

Next, since the order of output is based on *product* and *year*, dictionary is a useful data type to get the unique values (dict.keys) and frequencies (dict.values) of them. 

Then, two loops are developed to find the total number of complaints received for that product and year which is save as `num`. If num is greater than 0 (means there is complaint of this product in a specific year), a dictionary of company is created to calculate the total number of companies receiving at least one complaint for that product and year. And, the highest value of company dictionary will be used to calulate the highest percentage of total complaints filed against one company for that product and year.

----
### 3. Other questions
There are some other questions that need some tricks to fix. For example, the *year* and *product* should be sorted in chronological and alphabetical order, respectively. All string should be treated case insensitive, so I convert them to lowercase at the begining. Also, product with comma need to have double quotation mark added, and I choose to fix it at the process of writing `report.csv`.


Please see [demo.ipynb](https://github.com/kathy9980/consumer_complaints/blob/master/src/demo.ipynb) for more details.


by Kexin Song
