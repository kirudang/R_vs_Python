## **Critical differences**
This section highlights differences in Python and R that could result in inadvertent errors if the wrong convention is used (i.e. code may still run but would produce wrong result).

|**Topic**|**R**|**Python**|
| :-: | :-: | :-: |
|General purposes|R was developed specifically for statistical computing and data analysis.|Python was developed as a general-purpose programming language.|
|Boolean|<p>TRUE or T</p><p>FALSE or F</p>|<p>True</p><p>False</p>|
|Array indexing|Starts at 1|Starts at 0|
|Indentation|Has no impact on code – is purely cosmetic|Has a specific meaning in the code. Reducing the indentation level indicates the end of a block of code.|
|Length of a string|<p>nchar(x)</p><p>Do not use length(x)</p>|len(x)|
|Return statements in functions|If no return statement is specified, will return the last calculation done within the function|Return statement must be specified if we want the function to return an output; otherwise it will return “None”|
|Interpretation of “=”|The “=” sign will create an independent copy of the object. For example, if we do data\_2 = data\_1, and perform some manipulations on data\_2, then data\_1 will be unchanged. |<p>The “=” sign will create a new pointer to the original object, which will not behave independently. For example, if we do data\_2 = data\_1, and perform some manipulations on data\_2, the same operations will be applied to data\_1. </p><p>To make an independent copy of a dataset, use data\_2 = data\_1.copy() instead. </p>|
## **Structural differences**
This section highlights differences in Python and R that represent significant differences in the way the code is structured, but which are unlikely to cause non-obvious errors (i.e. if the wrong approach is used then the code would not run).

|**Topic**|**R**|**Python**|
| :-: | :-: | :-: |
|Code blocks|<p>Are encased in braces { and }</p><p>example = function(x){ </p><p>some code </p><p>some more code </p><p>return(something)</p><p>}</p>|<p>Begins with a line ending with a colon. On the next line, the indentation level increases by 1. The code block ends when the indentation level returns back to where it was at the start of the code block.</p><p>def example(x):</p><p>some code </p><p>some more code </p><p>return somethig </p><p>more code that is not part of the function definition</p>|
|Common ways to create unlabelled sequences of objects|<p>In R, these are called **vectors**. Use the “c” command to create one, e.g. c(1, 2, 3)</p><p>c here stands for combination.</p><p>Elements in an R vector must all be of the same type.</p>|<p>In Python, this is called a **list**. Use square brackets with elements separated by commas, e.g. [1, 2, 3]</p><p>Elements in a Python list can be of mixed type.</p><p>Can also create a tuple using round parentheses, but these cannot be changed after being created. Example: (1, 2, 3)</p>|
|Common ways to create labelled sequences of objects|<p>In R, this is called a **list**. Use the “list” command to create one, separating key-value pairs with an equal sign, e.g. l = list('a' = 1, 'b' = 2, 'c' = 3) </p><p>Access elements with the $ symbol, e.g. l$a is 1</p>|<p>In Python, this is called a **dictionary**. Use braces to create on, separating the list of key-value pairs with commas, e.g. d = {'a':1, 'b':2, 'c':3} </p><p>Access elements using square brackets, e.g. d['a'] is 1</p>|
|Applying a function across all elements of an array|Use the lapply command|Use the list comprehension syntax, e.g. [formula for x in list if condition]|
|Loop|for(i in 1:10) {...}|for i in range(10): ...|
|Conditional statement |if(x > 3) {...}|if x > 3: ...|
|Call a function|function(data)|<p>function(data)</p><p>data.function()</p><p>In Python, we have more ways to call a function, in which data oriented is a common way:</p><p>For example:</p><p>mean(data)</p><p>but we also call:</p><p>data.mean()</p>|
|Access a column in a data frame|<p>1.     Using the $ operator: data\_frame$column</p><p>2.     Using square brackets []: data\_frame[, "column"]</p>|<p>1.     Using square brackets []: data\_frame["column"]</p><p>2.     Using the dot notation: data\_frame.column (only works if the column name does not contain any spaces or special characters)</p>|
## **Minor Differences**
These are differences in naming or notational conventions that don’t cause major changes in the structure of a code, but which might result in needing to change the name of a keyword or function. Items in this list will cause an obvious error (e.g. code won’t run) if the wrong convention is used.

|**Topic**|**R**|**Python**|
| :-: | :-: | :-: |
|Concatenating strings|<p>Use “cat”, paste() or “paste0”</p><p>cat("Hello,", "world!")</p><p>Note: paste0() is similar to paste(), but it does not add any separator between the strings, while we can regulate the separator in paste(). For example, we can paste("Line 1", "Line 2", sep = "\n") to break line.</p>|<p>Use “+”</p><p>“Hello, " + "World!"</p><p>Other options: format(), join()</p><p>concatenated\_string = "{}{}".format(string1, string2)</p><p>concatenated\_string = "\_".join([string1, string2])</p>|
|Displaying text|Use “print” – this can only display a single string|Use the print command. This can handle a sequence of strings / variables and will print them all out with a space between them.|
|Exponentiation|Can use a \*\* b or a^b|Use a \*\* b|
|Modular arithmetic|Use a %% b|Use a % b|
|Integer division, discarding remainder|Use a %/% b|Use a // b|
|Determine type of a variable|Use typeof(x)|Use type(x)|
|Change type of a variable|General format of the function is “to.type()”. Example: to.integer(x)|General format of the function is “type()”. Example: int(x)|
|Boolean variables|Use all-caps, TRUE and FALSE|Capitalize only first letter, True and False|
|Boolean operators|<p>Use symbols &, |, !</p><p>For containment in a vector use %in%</p>|<p>Use keywords and, or, not</p><p>For containment in a list use in</p>|
|Install package|install.packages('name')|pip install name|
|Importing additional functionality|<p>These are called **packages** in R</p><p>Use library(package)</p><p>In R, when we access library, all functions of that library will be available.</p>|<p>These are called **modules** in Python</p><p>Use from package import module</p><p>from sklearn import metrics</p><p>Note: In Python, every import only does with a specific function from that library. So if you need to import all modules, you need to use below syntax:</p><p>from package import \*</p><p>For example:</p><p>from pandas import \*</p>|
|Comment out|Ctrl + Shift + C|<p>·        Windows: CTRL + 3</p><p>·        Mac: CMD + 3</p>|
|Create a function|<p>Use function()</p><p>function\_name <- function(arg1, arg2){ </p><p>return()</p><p>}</p>|<p>Use def()</p><p>def function\_name(arg1, arg2): </p><p>return()</p>|
|Lambda functions|<p>Do not have.</p><p>Still use using the function() keyword to create function.</p>|<p>Lambda functions are anonymous functions in Python, meaning they are functions without a name. They are used to perform a small task or calculation and are often used in combination with other functions like filter(), map() or reduce(). The syntax of a lambda function in Python is:</p><p>lambda arguments: expression</p><p>f = lambda x: x\*\*2 </p><p>print(f(5)) # 25</p>|
|Condition ifelse()|R offers this.|<p>Not offer. Need to use normal syntax:</p><p>result = x if x > y else y</p>|
|Call for help|<p>Type in Console:</p><p>?function\_name()</p><p>??function\_name()→ To check the package that contains the function.</p><p>For example:</p><p>?mutate()</p>|<p>Help(function\_name)</p><p>For example:</p><p>Help(len)</p><p>Note: Python also has dir(), a function used to return a list of valid attributes and methods of an object. For example, dir(list) returns a list of attributes and methods available for the built-in list type</p>|
|Check available built-in functions|ls("package:base") :This will return a character vector of all the functions in the base package or help(base) : see a list of all the functions in the base package, along with brief descriptions of each.|dir(\_\_builtins\_\_)|
|Unequal|!=|!= or <>|
## **Some differences in Data Manipulation**
These are differences in fundamental data cleaning steps when working with data frame.

In R, R Base and dplyr are two main libraries for data frame manipulation, when in Python, they are Python Base and Pandas.

|**Topic**|**R**|**Python**|
| :-: | :-: | :-: |
|Check structure|str(df)|df.info()|
|Data dimension|dim(df)|<p>df.shape</p><p>Note: No bracket here for shape</p>|
|Variables of data frame|colnames(df)|<p>df.columns</p><p>Note: No bracket here for columns</p>|
|Drop columns|<p>Single:</p><p>df$column <- NULL</p><p>Multiples:</p><p>·        By index</p><p>df[ , -c(column\_index\_1, column\_index\_2)]</p><p>·        By name</p><p>df[ , !names(data\_frame) %in% c("column\_name1", "column\_name2")]</p>|<p>Single:</p><p>del df["column\_name"]</p><p>or We can use below code with 1 column name.</p><p>Multiples:</p><p>df.drop(columns=["column\_1", "column\_2"], inplace=True)</p>|
|Check unique values|unique(df$column\_name)|<p>df["column\_name"].unique() df["column\_name"].value\_counts()</p><p>For value\_counts() we can state an argument normalize = True to calculate the proportion of each element in the column.</p>|
|Check duplicated observations|summary(duplicated(df))|df.duplicated().sum()|
|Drop duplicated values|<p>df[!duplicated(df), ]</p><p>or you can use dplyr as follow:</p><p>df %>% distinct()</p>|df.drop\_duplicates(inplace=True)|
|Check missing values|<p>·        Single column is.na(df$column\_name)</p><p>·        Multiple columns sapply(df, function(x) sum(is.na(x)))</p>|df.isnull().sum()|
|Drop NA|new\_df <- na.omit(df)|new\_df = df.dropna()|
|Fill NA|<p>We can use replace\_na() function in tidyr, or na.fill() from the zoo library,</p><p>or we can use R base like this:</p><p>df[is.na(df$col), "col"] <- value</p>|<p>It’s easier to replace NA in Python. We just need to specify column and value then conduct this code:</p><p>df.fillna(value)</p><p>df.column\_name.fillna(value)</p>|

