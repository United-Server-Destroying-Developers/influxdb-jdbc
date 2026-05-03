# Overview of JDBC driver

---
## What needs to be developed for JDBC driver

In a nutshell, you need to implement only 4 interfaces for bare minimum implementation:
- [Driver.java](https://docs.oracle.com/javase/8/docs/api/java/sql/Driver.html)
- [Connection.java](https://docs.oracle.com/javase/8/docs/api/java/sql/Connection.html)
- [Statement.java](https://docs.oracle.com/javase/8/docs/api/java/sql/Statement.html)
- [ResultSet.java](https://docs.oracle.com/javase/8/docs/api/java/sql/ResultSet.html)

In addition, for more comprehensive implementation and recognition from DB manager like DataGrip, DBeaver..., you need to implement further interfaces:

- [Callable Statement](https://docs.oracle.com/javase/8/docs/api/java/sql/CallableStatement.html) 
- [Database Metadata](https://docs.oracle.com/javase/8/docs/api/java/sql/DatabaseMetaData.html) 
- [Driver Action](https://docs.oracle.com/javase/8/docs/api/java/sql/DriverAction.html) 
- [Parameter Metadata](https://docs.oracle.com/javase/8/docs/api/java/sql/ParameterMetaData.html)
- [Prepared Statement](https://docs.oracle.com/javase/8/docs/api/java/sql/PreparedStatement.html)
- [ResultSet Metadata](https://docs.oracle.com/javase/8/docs/api/java/sql/ResultSetMetaData.html)

***NOTE:*** we will never achieve full JDBC support as latest InfluxDB version only implement parts of SQL.

Recommended reading: [java.sql docs](https://docs.oracle.com/javase/8/docs/api/java/sql/package-summary.html)

---

## What is implemented

After a quick glance it looks like there is implemented some parts of Driver, Connection, Statement and ResultSet.
Furthermore, there is implementation of PreparedStatements, but nothing is implemented.

---

## Steps from here now

I would suggest that we rewrite code and have for help forked code, as some implementations looks like magic, and I think
we will understand JDBC driver better if we rewrite it in our style.

Firstly, I would implement everything for different version controls of InfluxDB, as refactoring code
after making solid progress would be pain in the a**. 

I would start with implementation of **Driver.java**, as it is the main entry point of driver. After that we would implement Connection.java...


---
## References for implementing things

- [Introduction to JDBC](https://www.baeldung.com/java-jdbc)
- [Establishing JDBC Connection in Java](https://www.geeksforgeeks.org/java/establishing-jdbc-connection-in-java/)
- [Writing a custom jdbc driver in java a very basic one](https://stackoverflow.com/questions/28114725/writing-a-custom-jdbc-driver-in-java-a-very-basic-one)
- [Create your own type 3 JDBC driver, Part 1](https://www.infoworld.com/article/2163610/create-your-own-type-3-jdbc-driver-part-1.html)