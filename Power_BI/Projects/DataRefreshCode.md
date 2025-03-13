## Data Refresh Table How-To
I like listing when the data was last refreshed on my Power BI reports. 
To do this, I click “Enter Data” under Transform Data, set the table title to “Last Date Refresh” and enter this Power Query (M) code below to return the current date/time. 


    = let
    Source = #table(type table[LastRefresh=datetime], {{DateTime.LocalNow()}}),
    #"Changed Type" = Table.RenameColumns(Source,{{"LastRefresh", "Last Data Refresh"}})
    in
    #"Changed Type"
