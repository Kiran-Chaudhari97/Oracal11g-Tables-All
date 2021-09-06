# SQL-PLSQL-Oracal-11g
--==================================================================================================
--                            **********SQL Complete******
--==================================================================================================
--SQL Defination:- It is a Collection of per defined commands and constructs with syntactical rules
--==========================================================================================================================
--                        RDBMS (Relational Database Management System)
--===========================================================================================================================

--RDBMS is the basis for SQL, and for all modern database systems such as MS SQL Server, IBM DB2, Oracle, MySQL, and Microsoft Access.
--The data in RDBMS is stored in database objects called tables. 
--A table is a collection of related data entries and it consists of columns and rows.
--Look at the "Customers" table:

--==========================================================================================================================
--                            **********SQL Commands******
--===========================================================================================================================
--Types Of SQL Commands
--          |
--          |---> 1.DDL (DATA DEFINATION LANGUAGE)
--          |        |        USED TO CREATE OR CHANGE AND DELETE ANY DATABASE OBJECT
--          |        |
--          |        |--->CREATE
--          |        |
--          |        |--->ALTER
--          |        |
--          |        |--->DROP
--          |        |
--          |        |--->TRUNCATE
--          |        |
--          |        |--->RENAME

-------------------------------------------------------------------------------------------------------------------------
--          |---> 2.DML (DATA MANIPULATION LANGUAGE)
--          |        |        THESE COMMANDS ARE USED TO ENTER NEW DATA/CHANGING EXISTED DATA DELETING DATA FROM TABLE.
--          |        |
--          |        |--->INSERT
--          |        |
--          |        |--->UPDATE
--          |        |
--          |        |--->DELETE

--------------------------------------------------------------------------------------------------------------------------
--          |---> 3.DRL (DATA RETRIEVAL LANGUAGE)
--          |        |     _________________________________________________________________________________
--          |        |     |Querying the Data From Tables                                                   |
--          |        |     |Query --> It is an Opration That retrives Data from One or More Tables Or Views.|      
--          |        |     |________________________________________________________________________________|
--          |        |--->SELECT *NOTE (LOGIACAL COMMAND)
--                         The SELECT Statement is used to Retrive Data From One or More
--                              |
--                              |----Tables.
--                              |
--                              |----Object Tables.
--                              |
--                              |-----Views.
--                              |
--                              |-----Object Views.
--                              |
--                              |-----Materialized Viewes.
--
--
--------------------------------------------------------------------------------------------------------------------------
--          |---> 4.DCL (DATA CONTROL LANGUAGE)
--          |        |        USED TO CONTROL THE ACCESS OF DATA BASES OBJECTS .THESE COMMANDS ARE USED BY DBA(DARABASE ADMINISTRATOR)
--          |        |
--          |        |--->GRANT
--          |        |
--          |        |--->REVOKE

----------------------------------------------------------------------------------------------------------------------------
--          |---> 5.TCL (TRANSACTION CONTROL LANGUAGE)
--          |        |        USED TO SAVE OR CANCAL THE ACTION/TRANSACTION MADE ON TABLE DATA.
--          |        |
--          |        |--->COMMIT
--          |        |
--          |        |--->ROLLBACK
--          |        |
--          |        |--->SAVEPOINT
--          |        

--==========================================================================================================================
--
--===========================================================================================================================

--          |        
--          |
--          |
--          |
--          |
--          |
--          |
--          |
--          |
--          |
-----------------------------------------------------------------------------------------
--                            ****** SQL QUERYS ********
-----------------------------------------------------------------------------------------
CREATE TABLE STUDENT 
(
STUDID NUMBER(6),
FNAME VARCHAR2(30),
LNAME VARCHAR2(30),
DOJ DATE,
CITY VARCHAR2(10)
);
--==========================================INERST INTO================================--
INSERT INTO STUDENT 
                VALUES(
                2265,
                'KIRAN',
                'CHAUDHARI',
                '21-Jun-2021',
                'Dhule'
                );

    
-------------------------------------------------------------------------------------------------------
--                                Substitution Variables
-------------------------------------------------------------------------------------------------------

-- *These Variables are used to Store Values Temprorarily.
-- *The Values Can Be stored Temporarily through
--        *Single Ampersand(&)
--        *Double Ampersand(&&)
--    *DEFINE and ACCEPT Commands 
--*The Single Ampersand(&)Substitution Variable Applieds for each Instance When The SQL Statement is Create Or Executed.
--*The Double Ampersand(&&)Substitution Variable Applies for all Instance Unit That SQL Statement is Existing.
 
 ---=============                ================================================        ======================================
 ----                                         *Single Ampersand(&)
--                           “&” is used to create a temporary substitution variable. 
--                 You will be prompted to enter the value every time the variable is referenced.
 ---=============                ================================================        ======================================
            INSERT INTO STUDENT(STUDID,FNAME,LNAME,DOJ,CITY)
            VALUES
            (
            &STUDID,
            '&FNAME', 
            '&LNAME', 
            '&DOJ',
            'PUNE'
            );
 
 ---=============                ================================================        ======================================
 ----                                         *Double Ampersand(&&)
--                            “&&” is used to create a permanent substitution variable. 
--                                     You need to enter the value only once.
 ---=============                ================================================        ======================================
            INSERT INTO STUDENT(STUDID,FNAME,LNAME,DOJ,CITY)
            VALUES
            (
            &STUDID,
            '&FNAME', 
            '&LNAME', 
            '&&DOJ',------Double Ampersand(&&)-------
            '&CITY'
            );
            

--==========================================================================================================================
--
--===========================================================================================================================

SELECT * FROM STUDENT;
DROP TABLE STUDENT;

--==========================================================================================================================
--                                            SQL Erros And How To Solve...???
--===========================================================================================================================

                    INSERT INTO STUDENT 
                    VALUES
                    (
                    'KIRAN',
                    'CHAUDHARI',
                    'RAVINDRA' ---------- EXTRA DATA IN WITHOUT COLUM NOT EXIST
                    );
----SQL Error: ORA-00913: too many values "too many values" IF YOU ADD EXTRA DATA IN WITHOUT COLUM NOT EXIST --
                                --**Solve**--
----'RAVINDRA' is EXTRA DATA IN WITHOUT COLUM NOT EXIST REMOVE THIS DATA--




