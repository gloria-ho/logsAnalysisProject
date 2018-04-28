# Udacity IPND Final Project: Logs Analysis

## Goal:

You've been hired onto a team working on a newspaper site. The user-facing newspaper site frontend itself, and the database behind it, are already built and running. You've been asked to build an internal reporting tool that will use information from the database to discover what kind of articles the site's readers like.

The database contains newspaper articles, as well as the web server log for the site. The log has a database row for each time a reader loaded a web page. Using that information, your code will answer questions about the site's user activity.

The program you write in this project will run from the command line. It won't take any input from the user. Instead, it will connect to that database, use SQL queries to analyze the log data, and print out the answers to some questions.

## About This Program
This is the final project in the Intro to Programming Nanodegree. In this project we will practice interacting with a live database both from the command line and from our code. We will explore a large database with over a million rows. Finally, we will build and refine complex queries and use them to draw business conclusions from data.

This project makes use of the Linux-based virtual machine and the database that we're working with is running PostgreSQL. We will be using the psycopg2 Python module to connect to the database.

## Setup Requirements
This project makes use of the same Linux-based virtual machine (VM). To run the progream, you will need:
- Python2
- Vagrant which can be found at https://www.vagrantup.com/downloads.html
- VirtualBox which can be found at https://www.virtualbox.org/wiki/Downloads

You will need to download the following SQL script: [download newsdata.zip](https://d17h27t6h515a5.cloudfront.net/topher/2016/August/57b5f748_newsdata/newsdata.zip/) You will need to unzip the file and move `newsdata.sql` to the `vagrant` directory, which is shared with your virtual machine.

## How to Run
To run the virtual machine you will need to enter the command `vagrant up` followed by `vagrant ssh`.

To connect to the database and load the data, `cd` into the `vagrant` directory and use the command `psql -d news -f newsdata.sql`.

To execute the program, run 
```
python3 newsdata.py
```
 from the command line.


## Query Design
Each question is answered using a single query execution. Multiple subqueries are used, some using the `from` keyword and others using `left join`.


## Expected Output

What are the most popular three articles of all time?

1. : Candidate is jerk, alleges rival    338647  hits
2. : Bears love berries, alleges bear    253801  hits
3. : Bad things gone, say good people    170098  hits

Who are the most popular article authors of all time?

1. : Ursula La Multa     507594  hits
2. : Rudolf von Treppenwitz      423457  hits
3. : Anonymous Contributor       170098  hits
4. : Markoff Chaney      84557  hits

On which days did more than 1% of requests lead to errors?

1. : 2016-07-17  2.26 % errors
