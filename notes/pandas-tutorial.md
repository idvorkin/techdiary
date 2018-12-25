# Storing common incantations for ipython + pandas

#

##################################################

#### Jupyter set to window width

    # Resize Jupyter to window width
    from IPython.core.display import display, HTML
    display(HTML("<style>.container { width:95% !important; }</style>"))

#### Jupyter run on a linux box, access from linux.

    https://coderwall.com/p/ohk6cg/remote-access-to-ipython-notebooks-via-ssh

#### ipython magic commands

    %history -n
    %history -g <string> search for string
    %recall - put in editor
    %rerun - execute in editor

#### fix column width to match terminal

    pd.set_option('display.large_repr', 'truncate')
    pd.set_option('display.max_columns', 0)

#### List columns

    df.columns()

#### Sorting

    df.sort_index()
    df.sort_values()

### Working with categories

#### Convert column type to category

    df.column = df.column.astype("category")

#### Count values in category

    df.column = df.column.value_counts()

#### Histogram column

    df.groupby(df.column).apply(len)

#### Custom Apply to a row

    df.apply(axis="columns", func=myFuncThatTakesArowAsInput) # pretty darn slow.

### Pivoting

#### Simple pivot table by count

    pv = pd.pivot_table(df,index=pd.Grouper(freq='2W'), columns="column_1",values="column2", aggfunc='count')

#### Simple pivot table by percent change

    pv = pd.pivot_table(df,index=pd.Grouper(freq='2W'), columns="column_1",values="column2", aggfunc='count').pcnt_change()
