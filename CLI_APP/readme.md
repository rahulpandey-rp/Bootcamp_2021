# CLI To-Do App

This is a command line application for ToDo list for single user.

## Description

This app is designed to let user save their daily task and it can help manage their list of task.It use is to make people handle their task and know the status for any specific task.

It will save the title of the task and it will also note down the date of the creation of the task. It has feature to mark the status of the task to complete or incomplete.

In this app you can add a task, list all the task, update the title, delete any specific task, list all the task with their status, list task from a specific date to a specific date and search title matching a specific pattern.

## Features

## Getting Started

### Dependencies

* Python3.x
* Mysql
* Any Operating system(windows, Linux, Macos)

### Libraries- 
* Argparse(For extraction of command line argument)
* sqlalchemy(Orm used to connect mysql database with python)
* mysql-connnector-python
* re (regular expression)
* Tabulate(to show the data retrieved in table format)

### Installing
* Download the file [link] and run it in your terminal by providing the arguments.

### Execution
Run the script by giving any command below:

#### Showing list of task by different filter

##### To list all the task with their id and creation date.
* ``` --list ```
##### To list all the task with their id and creation date where the status of task is complete.
* ``` --list complete ```
##### To list all the task with their id and creation date where the status of task is incomplete.
* ``` --list incomplete ``` 
##### To list task created between specific date to another date.
* ```--list --start(optional) YYYY-MM-DD --end(optional) YYYY-MM-DD  ```


#### Adding a title in database

* ``` --create <title-name> ```

            
#### Editing a title in database

* ``` --edit-title -id (Taskid) -title (Updated title name) ```

#### Editing the status of any task in database

* ``` --edit-status -id (Taskid) -iscomplete (choice: True or False ) ```

#### Deleting single or multiple task from the database

* ``` delete <Taskid> ```
            
#### Search a titles containing a word 

* ``` --search <word to search> ```



### Examples

#### sample table -
```
+----+---------------------+------------------------------+------------+--------------+--------+
| id | created_at          | title                        | updated_at | completed_at | status |
+----+---------------------+------------------------------+------------+--------------+--------+
| 15 | 2021-09-11 02:56:36 | Organize party               | NULL       | NULL         |      0 |
| 16 | 2021-09-12 03:56:36 | Study Data structure         | NULL       | NULL         |      0 |
| 17 | 2021-09-13 04:56:36 | Complete Interview           | NULL       | NULL         |      0 |
| 18 | 2021-09-14 05:56:36 | Complete competency meeting  | NULL       | NULL         |      0 |
| 19 | 2021-09-15 06:56:36 | Make ToDo App                | NULL       | NULL         |      0 |
| 20 | 2021-09-16 07:56:36 | Complete HTML Assignment     | NULL       | NULL         |      0 |
| 21 | 2021-09-17 08:56:36 | Make github repository       | NULL       | NULL         |      0 |
| 22 | 2021-09-18 09:56:36 | Meet clients on site         | NULL       | NULL         |      0 |
| 23 | 2021-09-19 10:56:36 | Settle Credit card bill      | NULL       | NULL         |      0 |
| 24 | 2021-09-20 11:56:36 | Pay electricity bill         | NULL       | NULL         |      0 |
| 25 | 2021-09-20 12:56:36 | Organize meeting with HRSPOC | NULL       | NULL         |      0 |
| 26 | 2021-09-21 13:56:36 | Check sprint duration        | NULL       | NULL         |      0 |
| 27 | 2021-09-22 14:56:36 | Revise assessment criteria   | NULL       | NULL         |      0 |
| 28 | 2021-09-23 15:56:36 | Start course on django       | NULL       | NULL         |      0 |
+----+---------------------+------------------------------+------------+--------------+--------+

```
#### Listing all data 

``` python  <path to file> -- list ```
* Output - 
```
+------+------------------------------+---------------------+--------------+
|   Id | Title                        | Created_at          | Iscomplete   |
|------+------------------------------+---------------------+--------------|
|   15 | Organize party               | 2021-09-11 02:56:36 | False        |
|   16 | Study Data structure         | 2021-09-12 03:56:36 | False        |
|   17 | Complete Interview           | 2021-09-13 04:56:36 | False        |
|   18 | Complete competency meeting  | 2021-09-14 05:56:36 | False        |
|   19 | Make ToDo App                | 2021-09-15 06:56:36 | False        |
|   20 | Complete HTML Assignment     | 2021-09-16 07:56:36 | False        |
|   21 | Make github repository       | 2021-09-17 08:56:36 | False        |
|   22 | Meet clients on site         | 2021-09-18 09:56:36 | False        |
|   23 | Settle Credit card bill      | 2021-09-19 10:56:36 | False        |
|   24 | Pay electricity bill         | 2021-09-20 11:56:36 | False        |
|   25 | Organize meeting with HRSPOC | 2021-09-20 12:56:36 | False        |
|   26 | Check sprint duration        | 2021-09-21 13:56:36 | False        |
|   27 | Revise assessment criteria   | 2021-09-22 14:56:36 | False        |
|   28 | Start course on django       | 2021-09-23 15:56:36 | False        |
+------+------------------------------+---------------------+--------------+
```
#### Listing data with Date filter

###### List all task created from specific date to last
```
python  <path to file> -- list --start 2021-09-13
 ```
 
* Output
```
+------+------------------------------+---------------------+--------------+
|   Id | Title                        | Created_at          | Iscomplete   |
|------+------------------------------+---------------------+--------------|
|   17 | Complete Interview           | 2021-09-13 04:56:36 | False        |
|   18 | Complete competency meeting  | 2021-09-14 05:56:36 | False        |
|   19 | Make ToDo App                | 2021-09-15 06:56:36 | False        |
|   20 | Complete HTML Assignment     | 2021-09-16 07:56:36 | False        |
|   21 | Make github repository       | 2021-09-17 08:56:36 | False        |
|   22 | Meet clients on site         | 2021-09-18 09:56:36 | False        |
|   23 | Settle Credit card bill      | 2021-09-19 10:56:36 | False        |
|   24 | Pay electricity bill         | 2021-09-20 11:56:36 | False        |
|   25 | Organize meeting with HRSPOC | 2021-09-20 12:56:36 | False        |
|   26 | Check sprint duration        | 2021-09-21 13:56:36 | False        |
|   27 | Revise assessment criteria   | 2021-09-22 14:56:36 | False        |
|   28 | Start course on django       | 2021-09-23 15:56:36 | False        |
+------+------------------------------+---------------------+--------------+
```
###### List all task created upto specific date from start
``` 
python  <path to file> -- list --end 2021-09-18
```
* Output
```
+------+-----------------------------+---------------------+--------------+
|   Id | Title                       | Created_at          | Iscomplete   |
|------+-----------------------------+---------------------+--------------|
|   15 | Organize party              | 2021-09-11 02:56:36 | False        |
|   16 | Study Data structure        | 2021-09-12 03:56:36 | False        |
|   17 | Complete Interview          | 2021-09-13 04:56:36 | False        |
|   18 | Complete competency meeting | 2021-09-14 05:56:36 | False        |
|   19 | Make ToDo App               | 2021-09-15 06:56:36 | False        |
|   20 | Complete HTML Assignment    | 2021-09-16 07:56:36 | False        |
|   21 | Make github repository      | 2021-09-17 08:56:36 | False        |
|   22 | Meet clients on site        | 2021-09-18 09:56:36 | False        |
+------+-----------------------------+---------------------+--------------+
```

###### List all task created between between two dates
```
python  <path to file> -- list --start 2021-09-14 --end 2021-09-18
```
* Output
```
+------+-----------------------------+---------------------+--------------+
|   Id | Title                       | Created_at          | Iscomplete   |
|------+-----------------------------+---------------------+--------------|
|   18 | Complete competency meeting | 2021-09-14 05:56:36 | False        |
|   19 | Make ToDo App               | 2021-09-15 06:56:36 | False        |
|   20 | Complete HTML Assignment    | 2021-09-16 07:56:36 | False        |
|   21 | Make github repository      | 2021-09-17 08:56:36 | False        |
|   22 | Meet clients on site        | 2021-09-18 09:56:36 | False        |
+------+-----------------------------+---------------------+--------------+
```
