## Measures Used in Follow Through Analysis
Below is the list of measures and their DAX formulas used in this report. 

### % Highest Follow Through = 
    VAR ProgramFollowThrough = 
    ADDCOLUMNS(
        VALUES('Updated_Dummy_Data'[Program]),
        "Rate", 
        DIVIDE(
            CALCULATE(COUNTROWS('Updated_Dummy_Data'), 'Updated_Dummy_Data'[Enrolled] = "Followed Through"), 
            CALCULATE(COUNTROWS('Updated_Dummy_Data'))
        ))
    VAR MaxProgram = 
    TOPN(1, ProgramFollowThrough, [Rate], DESC)
    RETURN 
    CONCATENATEX(MaxProgram, 'Updated_Dummy_Data'[Program] & " - " & FORMAT([Rate], "0%"), ", ")

### % Didn't Attend Offer = 
    DIVIDE([Count Didn't Attend Offer],[Count All Offers])

### % Attended Offer = 
    DIVIDE([Count Attended Offer],[Count All Offers])
    
### Average Follow Through = 
    FORMAT([Attended Offer_Dummy] / DISTINCTCOUNT('Updated_Dummy_Data'[Program]),"0") & " students"

### Count Highest Follow Through = 
    VAR ProgramFollowThrough = 
    ADDCOLUMNS(
        VALUES('Updated_Dummy_Data'[Program]),
        "Count", 
            CALCULATE(COUNTROWS('Updated_Dummy_Data'), 'Updated_Dummy_Data'[Enrolled] = "Followed Through")
    )
    VAR MaxProgram = 
    TOPN(1, ProgramFollowThrough, [Count], DESC)
    RETURN 
        CONCATENATEX(MaxProgram, 'Updated_Dummy_Data'[Program] & " - " & [Count] & " students ", ", ")

### Count Didn't Attend Offer = 
    CALCULATE(
        COUNTROWS('Updated_Dummy_Data'),
        FILTER('Updated_Dummy_Data','Updated_Dummy_Data'[Enrolled]="Didn't Attend"))
        
### Count Attended Offer  = 
    CALCULATE(COUNTROWS('Updated_Dummy_Data'),FILTER('Updated_Dummy_Data','Updated_Dummy_Data'[Enrolled]="Followed Through"))

### Count All Offers = 
    COUNTROWS('Updated_Dummy_Data')

