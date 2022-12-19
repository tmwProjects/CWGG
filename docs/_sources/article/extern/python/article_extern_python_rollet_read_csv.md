# From Excel to Python  

## Assignment 1

### 1. Importing data
We start by loading the data as csv file... But beware!
Encoding error! A none default encoding of the csv is found by the IDE.
To import correctly change encoding in argument

    df = pd.read_csv('Ubung 1 Kamchatka.csv', sep=';', encoding='windows-1252', skipinitialspace = True) 
    pd.set_option('display.max_columns', None)      
                                                            
### 2. Clean up the data
Now that the data is imported we have a lot of columns to deal with. We don't need them so let's get them out.
This is done by calling the 'drop' function.

    df.drop(['units','sample','Age', 'volcano', 'location', 'sampletype', 'rocktype_div', 'refchem', 'longitude', 'latitude'], axis=1, inplace=True)                                        
Great, now we can work with the data set! Before we can start calculating things, we need to clean up this mess a little further. 

There are several types of errors that can occur, when try to work with the data. This includes:
* Non-zero Values (NaN) 
* excess Whitespace 
* letters in between numbers

An error that might occur when accessing the columns is the following: 

    -> 'Key Error = ' SiO '

This means there is an issue with the column name addressed. In order to find the error, the columns can be displayed 

    code for this goes here

The additional white space at any position can be removed by using the replace function. 

    df = df.str.replace(' ','')

There some others ways white space can be exspunged: 
*  If a csv_read method is used, the 'skipinitialspace' argument can be used to get rid of any intial white space
*   in the dataframe
*   The replace() or strip() function can be used on every column
*   One can write their own function to strip the dataframe of whitespace

In this example we will use the first way. Let's see if we can add the column now
In the next step we will address the clean up of the data we have.
to get rid of any lines that have no values in them, we apply:

    df = df.dropna(how='all')
Now we have a lot of NaN values. NaN resembles a non integer object and can lead to issues later.
Therefore we need to replace these values with actual zeros which can be done with:
    
    df = df.fillna(0)
It appears there is more to be done since our values appear to be objects
We can verify this with the info statement
    
    df.replace(to_replace=',', value='.', inplace=True)
    
This changes all values so they are recognized as numerical values
Even though there still seems to be an issue with the column 'MnO'
The issue here is whitespace in the middle of the value
Ridding values of the whitespace inbetween can be done by using the replace method
Whitespace is replaced by an truly empty space even though the white space is removed more errors occur!
At this point it is easier for just one value to just replace it by hand before you invest to much time.
    
    df['MnO']= df['MnO'].str.replace(' ','')
For some reason, MnO isn't recognized as an integer. We will fix that by casting the row as integer.
    
    df['MnO']=pd.to_numeric(df['MnO'])

Now since the data is cleaned up, we can get into calculating stuff.
We have to account for the Iron, so we have to recalculate all Fe2O3 to FeO
    
    df['FeOtot']=df['FeO']+((df['Fe2O3']/(2*Fe+3*O))*(2*(Fe+O)))
Since we don't need FeO and Fe2O3 no longer, the columns are dropped
    
    df.drop(['FeO', 'Fe2O3'], axis=1,inplace=True)
Also we should adapt our floating point numbers so they aren't to confusing
    
    pd.options.display.float_format = '{:.2f}'.format   
Let's start by making the sum for every sample in a new column
    
    df['sum']= df.sum(axis=1)
The next step in order to normalise the concentrations is to get rid of the LOI.
For this we can perform a substraction operation of the two coloumns
    
    df['sum']=df['sum']-df['LOI']
Let's also reset the index and get rid of the old!
    
    df=df.reset_index()
Since we don't need this coloumn anymore, we can drop it.
    
    df.drop(['LOI','index'], axis=1, inplace=True)

One can save the subtraction step by dropping the LOI column before summing up!
The next step is the actual normalising of the columns by making a normalising factor

    df['sum_norm']=100/df['sum']
    df.update(df.iloc[:, 1:13].mul(df.sum_norm, 0))

Now we calculate interesting Ion ratios

    df['MgO/FeO']= df['MgO']/df['FeOtot']
    df['Kation_Mg/Fe']= (df['MgO']/(Mg+O)*Mg)/(df['FeOtot']/(Fe+O)*Fe)
    df['Molverhältnis_Mg/Fe']= (df['MgO']/(Mg+O))/(df['FeOtot']/(Fe+O))
    
In order to plot a TAS diagramm we need the Total alkali value
    
    df['Alkali']=df['Na2O']+df['K2O']
    
Time to plot some graphs!
For that we will need to import matplotlib!

    df.plot(kind="scatter", x="SiO2", y="Alkali", s=20)
    df.plot(kind="scatter", x="SiO2", y="MgO", s=20)
    plt.show()

Congratulations, you have succesfully made your first Analysis and plotted some graphs by using Python! 
