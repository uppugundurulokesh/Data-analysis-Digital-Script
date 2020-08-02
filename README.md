# Data-analysis-Digital-Script
Data analysis digital script for some topics

# What is Pandas? Intraduction
Pandas is a one of the most popular python module for DataScience,Machine Learning and AI. It is one of the my personal favoriate library. It is extensivily use read data and process data, literely one of the best way for processing data.Wherever you have table data like rows and columns pandas provide bunch of libraries for processing data.

# Installation:
If your using jupyternotebook pandas is already installed predifind library no need to install again, otherwise you just use this command
* pip3 install pandas

After installation you can check the version using this command

    import pandas as pd      # Here we are importing the pandas library and set the object with name pd. you can use another name inplace of pd
    print(pd.__version__)    # Here we are checking the version of pandas

I hope now it is clear upto now, if it is clear we will move forward

# Types of pandas for data processing:
Pandas is mainly divided into two types 1) Series 2) DataFrame, ok,we will discuss with examples

# Pandas Series:
Series means it is a one dimensional array, we can do data processing using one dimensional arrary. let see some examples,

Here I am importing pandas library with object name pd and I call the series with pandas object and I just know the type of "s" using print statement
   
    #Series:
    import pandas as pd
    s=pd.Series()
    print('{}\n'.format(s))

* Now, assign some values to series and print the values

      import pandas as pd
      s=pd.Series([1,2,3.3])
      print(s)
      
* Now, assign numpy values to series and print the values

      import numpy as np
      import pandas as pd
      n=np.array([1,2,3])
      s=pd.Series(n)
      print(s)
      
      # convert int to float
      s1=pd.Series(n,dtype=np.float32)
      print(s1)
   
* If you observe in output we are finding some index values, then let see how to change the index's

      s=pd.Series([1,2,3],index=['a','b','c']) # using index property name we can change index's
      print(s)
      
* Now, see how to access the data from series, we already see how to access the data in list concepts,so, same way we can access data. lets see with examples

        import pandas as pd
        import numpy as np
        n=np.array([1,2,3,"hello","nice day",12.45])
        s=pd.Series(n)
        print(s)
        
        # update the data
        s[0]=100
        print(s)
        
        # access the data
        print(s[0])
        # print the data in range
        print(s[1:3])   # starting index:ending index
        print(s[:4])  

        # print the data in reverse order
        print(s[::-1])

ok, fine this is the way we can create the series and access the data from series, we will do some more examples of series in dataframes. I hope it is clear, now we will discuss about DataFrames

# Pandas DataFrames - Intraduction:
DataFrame is a main object in pandas. It is used to represent data with rows and columns. simply it is a two dimensional array. DataFrame provide a major key roll in Datascience for data manipulation. DataFrame is a datastructure represent data in tabular or excel spread sheet(like data). I hope it is clear. We will see the how to create dataframes and what we do data operations using dataframes with examples. let's start

Here we will importing pandas library with object name as pd, and we will see how to pass list,dictionaries,numpy values to dataframe and how to ready csv files,excel files,json files etc using dataframes, ok let's start with examples

* Create DataFrame:

        import pandas as pd
        df=pd.DataFrame()     # Here, by using pandas object we are create a dataframe and pass the reference to df variable
        type(df)              # Here just know the type of variable

* Now, we know how to create DataFrame using pandas then pass the list of values to dataframe

        import pandas as pd
        l=[[1,2,3],[4,5,6],[7,8,9],[10,11,12]]  # Here, we take 2d array values into reference variable name "l"
        df=pd.DataFrame(l)                      # Here, pass the list object "l" to DataFrame
        print(df)
      
* If you observe the output of above program we get the values with rows and columns along with column names 0,1,2 and some index values based on values of list, then let's see how to change columns names and index names
* Change the column names and index names:

        import pandas as pd
        l=[[1,2,3],[4,5,6],[7,8,9],[10,11,12]]
        df=pd.DataFrame(l,columns=['a','b','c'],index=['row1','row2','row3','row4'])
        df
        
 * I hope it is clear, Now see how to pass the numpy values to DataFrame:
 
        import pandas as pd
        import numpy as np
        n=np.array([[1,2],[3,4],[5,6]])
        df=pd.DataFrame(n,columns=['a','b'],index=[1,2,3])
        df
        
 * Now, let's check dictionaries to DataFrame:
 
        import pandas as pd
        df=pd.DataFrame({'a':[1,2,3],'b':[4,5,6]})  # here, we are passing dictionaries to DataFrame
        df
        
* Now, pass the list of tuples to DataFrame:

        #using list of tuples
        import pandas as pd
        student=[("sai",34),("ganesh",35),("ram",45)]
        df=pd.DataFrame(student,columns=['sname','smarks'])
        df
* Upto now we just learn how to create DataFrame and how to pass different types of values to DataFrame, hope it is clear
* Now, we will learn how to read the different files like csv files, excel files, json files etc
* Read data from csv files, what is csv(comma seperated values) means each column values in a table seperate with comma ex: 101,saiganesh,950 so, this files are called comma seperated values. let's see how to read csv files using pandas into dataframe ok,
* we can read csv files by using simple one line i.e pd.read_csv("filename.csv")
* Now see with example: create one weather.csv file and place that file into your working directory like below example
        
        	est	      temparature	winspeed	humidity	event
        	1/2/2019	30	            12	      12.50	     rain
        	1/2/2019	33	            14	      14.23	     rain
        	1/3/2019	43	            13	      43.13	     rain
        	1/4/2019	55	            8	      55.80	     fullair
        	1/5/2019	66	            10	      66.10 	 cold
        	1/6/2019	34	            15	      34.15	     cold
        
* Read Data from .csv file:

        import pandas as pd
        df=pd.read_csv('weather.csv')   
        df

* You can also read data from excel,html(hyper text markup language) and json(java script object notation) by using below syntax
    * pd.read_excel("filename/url")  # Reading data from excel sheet
    * pd.read_html("filename/url")   # Reading data from html table
    * pd.read_json("filename/url")   # Reading data from json


* Now, see how to convert csf file to json file:

        #convert csv to json
        import pandas as pd
        df=pd.read_csv('weather.csv')
        jsondata=df.to_json(orient="records")    
        jsondata
        
 * Now, we have json data. let's see how to read json data to DataFrame

        import pandas as pd
        dff=pd.read_json(jsondata)
        dff

* Upto now we are creating DataFrame, let's see how to access data from DataFrame
### Data Operations in DataFrame:

    import pandas as pd
    df=pd.read_csv('weather.csv')
    print(df.shape)   # find the dimention of data i.e how many rows and how many columns
    print(df.head())  # display top 5 rows as default  and we can use df.head(10) 
    print(df.tail())  # display bottom 5 rows of data
    print(df.columns)  # print the columns names
    print(df[2:5])     # get the rows using slicing
    
    #find the mean
    df[['temparature']].mean()  # one column mean

    #find the median
    df['temparature'].median()   # one column median

    #find the describe of data
    df[['temparature']].describe()  # one column describe 
   
    df.describe()    # all columns describe
    df.mean()   # all columns mean
    df.median()  # all columns median
* Get the one columns data:

        # get the one column
        #df.est (or)
        df['est']
        print(type(df['est']))  # find the type of df. if we use single [] then return series
        print(type(df[['est']])) # if we use double [[]] then return data frame
        
 * Get the two or more columns data:
 
        # get more than one column
        df[['est','temparature']].head()
        
 * Select the rows using condition based, Here we will get maximum temparature value
 
         # select the row which have maximum temparature
         df['temparature'].max()  # find the maximum value 
         df['temparature']==df['temparature'].max() #  return the boolean value of max
         df[df['temparature']==df['temparature'].max()] # return the row(dataframe) of max
         df[['est','temparature']][df['temparature']==df['temparature'].max()] # return the only two columns of max value
         
 * More than two conditions
    
        mydf=df[(df['temparature']>=60) & (df['event']=='cold')]
        mydf
        
 

