
# Storing common incantations for ipython + pandas
#
##################################################


#### ipython magic commands

    %history 
    %recall - put in editor
    %rerun - execute in editor

#### fix column width to match terminal

    pd.set_option('display.large_repr', 'truncate')
    pd.set_option('display.max_columns', 0)

#### List columns

    df.columns()


### Working with categories 

#### Convert column type to category

    df.column = df.column.astype("category")

#### Histogram column

    df.groupby(df.column).apply(len)
