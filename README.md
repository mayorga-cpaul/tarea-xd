SQL SYSDATETIME Function
SQL Server SYSDATETIME function is a Date Function, which is used to return the Current Date and Time of the computer on which the Server instance is running. The syntax of the SYSDATETIME Statement is

SYSDATETIME()
SQL Server SYSDATETIME Function Example
The SYSDATETIME function returns the datetime2 data type. And the format is: ‘yyyy-mm-dd hh:mm:ss.nnnnnnn’ (you can see that the fractional seconds precision = 7).
SELECT SYSDATETIME() AS [Current_Date]
Current Date and Time 1
NOTE: This function is similar to the GETDATE (), and the differences are:

It returns the fractional seconds precision up to 7, whereas the GETDATE returns up to 3
It returns datetime2 as the data type, whereas the GETDATE returns DateTime
SYSDATETIME Function Example 2
In this example, we are going to show you the SQL Server SYSDATETIME examples.

In the first three statements, we used the DATEPART to display the Milliseconds, Microseconds, and Nanoseconds from today’s date & time.
Next, we used the DATENAME in SQL Server to display the weekday name from today’s date & time.

in the last line, we used the DATEADD to display the Tomorrow date & time

SELECT 'Today' AS 'TODAY', SYSDATETIME() AS [Current_Date];

SELECT 'Milli Seconds' AS 'MILLI', DATEPART(millisecond, SYSDATETIME()) AS [Milli_Seconds]; 
SELECT 'Micro Seconds' AS 'MICRO', DATEPART(microsecond, SYSDATETIME()) AS [Micro_Seconds]; 
SELECT 'Nano Seconds' AS 'NANO', DATEPART(nanosecond, SYSDATETIME()) AS [Nano_Seconds]; 

SELECT 'Day' AS 'DAY', DATENAME(WEEKDAY, SYSDATETIME()) AS [Day_Name]; 

SELECT 'Tomorrow' AS 'DAY', DATEADD(day, 1, SYSDATETIME()) AS [Next_Date];
SQL SYSDATETIME Function 2
Example 3
In this Date Function example, we use the DATEDIFF function to check for Employee details. That includes What year we hired him, how many weeks he associated with our company, etc.
SELECT [FirstName] + ' '+ [LastName] AS [Full Name]
      ,[Occupation]
      ,[YearlyIncome]
      ,[HireDate]
      ,DATEDIFF (year, [HireDate], SYSDATETIME()) AS [YEARS]
      ,DATEDIFF (day, [HireDate], SYSDATETIME()) AS [DAYS]
      ,DATEDIFF (WEEK, [HireDate], SYSDATETIME()) AS [WEEKS]
      ,DATEDIFF (WEEKDAY, [HireDate], SYSDATETIME()) AS [WEEKDAY]
  FROM [Employes]
From the below screenshot, you can observe that we are finding the difference between the Employee Hire date and Today’s system date & time (SYSDATETIME()) using the DATEDIFF function.

SQL SYSDATETIME Function 3
