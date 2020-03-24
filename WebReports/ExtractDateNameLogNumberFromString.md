# Constants:
Constant Name | Constant Value | Constant Type
--- | --- | ---
# Parameters:
Parameter Name | Display Text | Prompt | Mandatory | Prompt Order | Type | Default Value | Description
--- | --- | --- | --- | --- | --- | --- | --- 
inputstring | (blank) | N | N | (blank) | string | IS-03/02/2013-Clark Kent-1603-0032 | (blank)
# ReportView:
```html
[/* Title: Blank Reportview */]

[/* Extract the Date, Name and Log Number from a string with the form: 

IS-03/02/2013-Clark Kent-1603-0032

or IS-<Date>-<Name>-<Log Number>

*/]
[LL_REPTAG_&inputstring /]

[LL_REPTAG_&inputstring PATCHANGE:"IS-<?+>-<[A-Z0-9a-z]+>-<[A-Z0-9a-z]+>":"Date: #1; Name: #2; Log Number: #3" SETVAR:NewName CURRENTVAL HIDE /]<BR>

<strong>[LL_REPTAG_%NewName CURRENTVAL /]</strong>
[LL_WEBREPORT_STARTROW /][LL_WEBREPORT_ENDROW /]
```
