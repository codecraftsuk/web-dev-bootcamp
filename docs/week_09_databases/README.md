# 1. Introduction to Databases

## 1.1 What is a database?

A database is a structured collection of data that is organized and stored in a way that allows for efficient retrieval, manipulation, and management of the data. It serves as a central repository for storing and managing vast amounts of information, ranging from simple lists to complex interconnected data.

In a database, data is typically organized into tables, which consist of rows and columns. Each row represents a single instance or entry in the table, while each column represents a specific piece of data stored in the table. Tables are used to represent entities or concepts, and the relationships between tables are established using keys (e.g., primary keys and foreign keys).

The data in a database can be queried and manipulated using specialized languages such as SQL (Structured Query Language). SQL allows users to perform operations such as retrieving specific data, filtering and sorting data, inserting and updating records, and creating relationships between tables.

## 1.2 Why are databases important?

Databases are crucial for efficient data management and play a significant role in various industries. They provide structured organization for data, eliminating redundancy and ensuring data consistency. By using databases, users can quickly retrieve specific information or subsets of data through queries, saving time and effort. The enforcement of data integrity rules and constraints ensures the accuracy and reliability of stored data.

Data security is another important aspect of databases, with access control mechanisms and encryption protecting sensitive information from unauthorized access and data breaches. Databases are also highly scalable, capable of handling large volumes of data and accommodating growing storage needs. The durability of data storage in databases ensures data persists even in the face of system failures.

Databases serve as a foundation for data analysis, enabling organizations to gain insights, make data-driven decisions, and improve operational efficiency. By leveraging databases, businesses can drive innovation, identify trends, and strategically plan for the future. Overall, databases are integral to effective data management, retrieval, security, and analysis, empowering organizations to succeed in the data-driven world we live in.

## 1.3 Basic example of a database

Imagine you have a physical address book where you store contact information for your friends and family. Each entry in the address book represents a person, and you have specific fields for their name, phone number, email address, and home address.

In this example, the address book serves as a simple database. Each page or entry in the address book corresponds to a row in the database, and each field (name, phone number, email, address) represents a column in the database.

Here is an example of how the tables may look:

| Name    | Phone Number  | Email                | Address        |
|---------|---------------|----------------------|----------------|
| John    | 123-456-7890  | john@example.com     | 123 Main St    |
| Sarah   | 987-654-3210  | sarah@example.com    | 456 Elm Ave    |
| Michael | 555-123-4567  | michael@example.com  | 789 Oak Ln     |


| Name       | Description            |
|------------|------------------------|
| Friends    | Close friends          |
| Family     | Immediate family       |
| Colleagues | Work-related contacts  |

With this address book database, you can perform operations such as retrieving contact information by looking up a person's name, updating a phone number if it changes, or adding new entries for new contacts.

Similarly, you can apply basic database concepts to organize, search, and manage your contact information effectively. While this example may not involve the complexities of modern database management systems, it demonstrates the fundamental concept of storing and retrieving data in a structured manner.

## 1.4 Types of Databases

There are many types of databases. The most common ones are:

- *Relational Databases*: Relational databases store data in tables with predefined relationships between tables. They use Structured Query Language (SQL) for data manipulation and retrieval. Examples include MySQL, Oracle, and PostgreSQL.

- *NoSQL Databases*: NoSQL (Not only SQL) databases are non-relational databases that store data in a variety of formats, such as key-value pairs, documents, or graphs. They are used for handling unstructured and rapidly changing data. Examples include MongoDB, Cassandra, and Redis.

- *Object-Oriented Databases*: Object-oriented databases store data in the form of objects, similar to object-oriented programming concepts. They are used for storing complex data structures and are often used in conjunction with programming languages. Examples include db4o and ObjectDB.

- *Hierarchical Databases*: Hierarchical databases organize data in a tree-like structure, with parent-child relationships. They are primarily used in legacy systems and are less commonly used today.

- *Network Databases*: Network databases are similar to hierarchical databases but allow for more complex relationships between data elements. They are also less commonly used today.


## 1.5 Relational Databases

Relational databases are a specific type of database management system (DBMS) that follows the principles of the relational model. In a relational database, data is organized into tables, with each table representing an entity or concept, and the relationships between tables are established using keys. Relational databases are widely used due to their simplicity, flexibility, and ability to handle complex data relationships.

- Tables: Data is stored in tables consisting of rows and columns. Each table represents a specific entity or concept, and each row represents a unique record or instance of that entity. Columns define the attributes or properties of the entity.

- Keys: Relational databases use keys to establish relationships between tables. A primary key uniquely identifies each row in a table, while foreign keys establish relationships by referencing the primary key of another table. These keys ensure data integrity and enable efficient data retrieval through joins across related tables.

- Structured Query Language (SQL): Relational databases use SQL as the standard language for managing and manipulating data. SQL provides a set of commands and queries to create, retrieve, update, and delete data in the database. It allows for complex operations such as filtering, sorting, grouping, and aggregating data.

Let's demonstrate a relational database based on the phonebook example.

| ContactID | Name    | Phone Number  | Email                | Address        |
|-----------|---------|---------------|----------------------|----------------|
| 1         | John    | 123-456-7890  | john@example.com     | 123 Main St    |
| 2         | Sarah   | 987-654-3210  | sarah@example.com    | 456 Elm Ave    |
| 3         | Michael | 555-123-4567  | michael@example.com  | 789 Oak Ln     |


| CategoryID | Name       | Description            |
|------------|------------|------------------------|
| 1          | Friends    | Close friends          |
| 2          | Family     | Immediate family       |
| 3          | Colleagues | Work-related contacts  |


In the "Contacts" table, each contact has a unique identifier called "ContactID." This column serves as the primary key of the table. It uniquely identifies each contact and ensures data integrity within the table.

The "Categories" table also has a unique identifier called "CategoryID," which serves as the primary key for this table. It uniquely identifies each category.

To establish a relationship between the "Contacts" and "Categories" tables, we can introduce a foreign key in the "Contacts" table. In this case, we'll add a column called "CategoryID" in the "Contacts" table. This column references the "CategoryID" column in the "Categories" table.

By linking the two tables using the foreign key, we can associate each contact with a specific category. For example, John (ContactID: 1) has a CategoryID of 1, which corresponds to the "Friends" category in the "Categories" table.

This relational database structure allows us to perform various operations. For instance, we can:

- Retrieve all contacts in the "Friends" category by joining the "Contacts" and "Categories" tables based on the CategoryID.
- Update the phone number for a specific contact by referencing their ContactID.
- Add new contacts and assign them to existing or new categories.
- Generate reports showing contacts grouped by categories.


We will focus on relational databases because they offer the opportunity to learn how to query data using SQL, which is a widely used and powerful language for database management. Additionally, understanding relational databases is valuable for working with frameworks like Django, as they utilize structured relational tables to organize and manipulate data efficiently.

# 1.6 Database Management Systems (DBMS)

A DBMS is software that enables the creation, management, and manipulation of databases. It provides an interface for users to interact with the database, perform queries, and manage data.

Some popular DBMSs include MySQL, Postgres, Oracle Database, Microsoft SQL Server, SQLite, and MongoDB.

DBMSs handle tasks such as data storage, data retrieval, data security, concurrency control, and query optimization.


# 2. SQL Fundamentals

We will be learning SQL with a particular focus on utilising PostgreSQL as our database management system.

## 2.1 Downloading Postgres

Postgres can be downloaded by following the instructions below:

1. Visit the official PostgreSQL website at https://www.postgresql.org/.

2. On the homepage, locate the "Download" button and click on it.

3. You will be redirected to the download page. Here, you will see different versions of PostgreSQL available for various operating systems.

4. Choose the appropriate version for your operating system. For example, if you're using Windows, select the Windows version; if you're using macOS, select the macOS version, and so on.

5. Once you have selected the version for your operating system, you will see a list of available installers.

6. Click on the installer that matches your system architecture (32-bit or 64-bit). If you're unsure, you can usually find this information in your system settings.

7. The download will begin automatically. Depending on your internet connection speed, it may take a few moments to complete.

8. Once the download is finished, locate the downloaded installer file on your computer.

9. Double-click on the installer file to start the installation process.

10. Follow the on-screen instructions provided by the installer. You may need to accept the license agreement, choose an installation location, and configure additional settings.

11. During the installation, you will be prompted to set a password for the default database superuser, usually named "postgres." Make sure to choose a strong password and remember it for future use.

12. Complete the installation by following the remaining steps in the installer. If prompted about applications you would like to install, under Database Server, select the intalled one and continue.

13. After the installation is complete, you should find PostgreSQL installed on your computer.

14. You can now launch the PostgreSQL command-line tool (psql) or use graphical interfaces like pgAdmin or DBeaver to interact with the PostgreSQL database.
 
## 2.2

## 2.3

## 2.4

# 3. Practice Questions

