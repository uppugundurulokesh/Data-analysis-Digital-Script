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
   
* If you observe in output we are finding some index value, then let see how to change the index's

      s=pd.Series([1,2,3],index=['a','b','c']) # using index property name we can change index's
      print(s)

