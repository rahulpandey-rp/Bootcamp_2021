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
* Libraries- 
            argparse(For extraction of command line argument)
            sqlalchemy(Orm used to connect mysql database with python)
            mysql-connnector
            re(regular expression)
            Tabulate(to show the data retrieved in table format)
* Any Operating system(windows, Linux, Macos)

### Installing
* Download the file [link] and run it in your terminal by providing the arguments.

### Execution
Run the script by giving any command below:

#### Showing list of task by different filter

##### T list all the task with their id and creation date.
* ``` --list ```
##### To list all the task with their id and creation date where the status of task is complete.
* ``` --list complete ```
##### To list all the task with their id and creation date where the status of task is incomplete.
* ``` --list incomplete ``` 
##### To list task created between specific date to another date.
* ```--list start(optional) YYYY-MM-DD end(optional) YYYY-MM-DD  ```


#### Adding a title in database

* ``` --create <title-name> ```

            
#### Editing a title in database

* ``` --edit-title -id (Taskid) -title (Updated title name) ```

#### Editing the status of any task in database

* ``` --edit-status -id (Taskid) -iscomplete (choice: True or False ) ```

#### Deleting a task from the database

* ``` delete <Taskid> ```
            
#### Search a titles containing a word 

* ``` --search <word to search> ```
