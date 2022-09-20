## SQL SYSDATETIME Function
>SQL Server SYSDATETIME function is a Date Function, which is used to return the Current Date and Time of the computer on which the Server instance is running. The >syntax of the SYSDATETIME Statement is

`SYSDATETIME()`

```
Ejemplo de función SYSDATETIME de SQL Server
La función SYSDATETIME devuelve el tipo de datos datetime2. Y el formato es: 'aaaa-mm-dd hh:mm:ss.nn' (se puede ver que la precisión de segundos fraccionarios = 7).
SELECT SYSDATETIME() AS [Current_Date]

Fecha y hora actuales 1
NOTA: Esta función es similar a GETDATE (), y las diferencias son:

Devuelve la precisión de fracciones de segundos hasta 7, mientras que GETDATE devuelve hasta 3
Devuelve datetime2 como tipo de datos, mientras que GETDATE devuelve DateTime
Ejemplo de función SYSDATETIME 2
En este ejemplo, vamos a mostrarle los ejemplos de SQL Server SYSDATETIME.

En las tres primeras declaraciones, usamos el DATEPART para mostrar los milisegundos, microsegundos y nanosegundos de la fecha y hora de hoy.
A continuación, usamos el DATENAME en SQL Server para mostrar el nombre del día de la semana de la fecha y hora de hoy.
```


## SYSDATETIME() Function in SQL Server

SYSDATETIME() :

This function in SQL Server is used to return the computer’s date and time in which the SQL Server is operating at present.

Features :

This function is used to find the computer’s date and time in which the SQL Server is operating.
This function comes under Date Functions.
This function doesn’t accept any parameter.
This function returns the output in ‘YYYY-MM-DD hh:mm:ss.mmm’ format.
Syntax :

SYSDATETIME()
Parameter :

This method doesn’t accept any parameter.

Returns :

It returns the computer’s date and time in which the SQL Server is operating in a ‘YYYY-MM-DD hh:mm:ss.mmm’ format.

Example-1 :

Using SYSDATETIME() function and getting the output.

SELECT SYSDATETIME();
Output :

2021-01-03 17:49:28.0575187
Here, the output will vary each time the code is compiled as this method returns the current date and time.

Example-2 :

Using SYSDATETIME() as a default value in the below example and getting the output.
```
CREATE TABLE system_date_time
(
   id_num        INT IDENTITY,
   message        VARCHAR(150) NOT NULL,
   generated_at DATETIME NOT NULL
   DEFAULT SYSDATETIME(),
   PRIMARY KEY(id_num)
);
INSERT INTO system_date_time(message)
VALUES('Its the first message.');

INSERT INTO system_date_time(message)
VALUES('system_date_time');

SELECT
     id_num,
     message,
     generated_at
FROM
     system_date_time;
```
Output :


| id_num  |   message              |   generated_at       |
| :------ | :--------------------- | :------------------- |  
| 1     | Its the first message.| 03.01.2021 18:53:56|
| 2     | system_date_time      | 03.01.2021 18:53:56|


Here, firstly you need to create a table then insert values into it then generate the required output using the SYSDATETIME() function as a default value.

Note: For running the above code use SQL server compiler, you can also use an online compiler.

Example-3 :

Using CONVERT() function in order to translate the output of the SYSDATETIME() function into the current date only.

```
SELECT CONVERT(DATE, SYSDATETIME());
```
Output :

2021-01-07
Here, the output may vary every time you run the code as it returns the current date.

Example-4 :

Using CONVERT() function in order to translate the output of the SYSDATETIME() function into the current time only.

```
SELECT CONVERT(TIME, SYSDATETIME());
```
Output :

06:20:12.2400986
Here, the output may vary every time you run the code as it returns the current time.

Application :

This function is used to return the current date and time of the computer in which the SQL server is operating.
