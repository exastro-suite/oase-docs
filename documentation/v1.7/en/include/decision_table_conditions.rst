.. csv-table:: Conditional expressions when creating Decision tables
   :name: decision_table_conditions
   :header: Conditional expression, Description, Message example, True condition input example
   :widths: 20, 40, 20, 20

   Equal(number),Is true if the numeric value of the acquired message is the same as the specified condition numeric value.,0,0
   Not equal(number),Is true if the numeric value of the acquired message is not the same as the specified condition numeric value.,0,10
   Equal(string),Is true if the string value of the acquired message is the same as the specified condition string.,Error,Error
   Not equal(string),Is true if the string value of the acquired message is not the same as the specified condition string.,Error,Warning
   Greather than,Is true if the numeric value of the acquired message is greather than the specified condition numeric value.,70,80
   Greather than or equal to,Is true if the numeric value of the acquired mesasge is greater than or equal to the specified condition numeric value.,70,80
   Less than,Is true if the numeric value of the acquired message is less than the specified condition numeric value.,70,60
   Less than or equal to,Is true if the numeric value of the acquired message is less than or equal to the specified condition numeric value.,70,60
   Matches the regular expression,Is true if the character string matches the condition's regular expression.,"A DB connection error has occurred","^.*An error has occurred.*$"
   Do not match regular expressions,Is true if the character string does not match the condition's regular expression.,"A DB connection error has occurred","^.*A warning has occurred.*$"
   Including,Is true if the acquired message list contains a value specified in the condition.,"[www01, www02, db01, ...]","www01"
   Not including,Is true if the acquired message list does not contain a value specified in the condition.,"[www01, www02, db01, ...]","www03"
   Time [HH:mm](From-to),Is true if the time in the acquired message matches the time period set by the condition."12:00", " Input "08:00" (From) to "18:00" (To)"