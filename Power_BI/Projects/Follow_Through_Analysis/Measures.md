### Highest Follow Through Rate = 
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

### Highest Follow Through Count = 
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

### Didn't Attend Offer_Dummy = 
    CALCULATE(
        COUNTROWS('Updated_Dummy_Data'),
        FILTER('Updated_Dummy_Data','Updated_Dummy_Data'[Enrolled]="Didn't Attend"))
