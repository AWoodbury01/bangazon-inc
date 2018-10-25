# Introduction to SQL with Music History

## Setup

```sh
mkdir -p ~/workspace/csharp/exercises/music-sql && cd $_
touch queries.sql
```

> **Note:** The `.sql` extension is common practice for files storing SQL queries


## Downloading the Database Files

Download the [musichistory.db](https://github.com/nashville-software-school/bangazon-inc/blob/master/orientation/exercises/assets/musichistory.db?raw=true) file, and then copy it to the folder that you created for this exercise. That file **is** the database. It contains all of the tables and data.

## References

* [SQLBolt Learn SQL with simple, interactive exercises.](https://sqlbolt.com/)
* [Introductory SQL tutorial](http://www.sqlcourse.com/)
* [W3schools interactive SQL tutorial](https://www.w3schools.com/sql/sql_intro.asp)
* [Online SQLite tutorial](http://www.sqlitetutorial.net/)

## Instructions

1. Open up the database file in the *DB Browser for SQLite* application to see it.
1. Go ahead and click around a little bit to familarize yourself with the database.
1. When you're ready to start the exercise, click the tab labeled "Execute SQL", type in your query and run it.

For each of the following exercises, provide the appropriate query. Yes, even the ones that are expressed in the form of questions. Everything from class and the [Sqlite](http://www.sqlite.org/) documentation for SQL [keywords](https://www.sqlite.org/lang.html) and [functions](https://www.sqlite.org/lang_corefunc.html) is fair game.

1. Query all of the entries in the `Genre` table
1. Using the `INSERT` statement, add one of your favorite artists to the `Artist` table.
1. Using the `INSERT` statement, add one, or more, albums by your artist to the `Album` table.
1. Using the `INSERT` statement, add some songs that are on that album to the `Song` table.
1. Write a `SELECT` query that provides the song titles, album title, and artist name for all of the data you just entered in. Use the [`LEFT JOIN`](https://www.tutorialspoint.com/sql/sql-using-joins.htm) keyword sequence to connect the tables, and the `WHERE` keyword to filter the results to the album and artist you added.
    > **Reminder:** Direction of join matters. Try the following statements and see the difference in results.

    ```
    SELECT a.Title, s.Title FROM Album a LEFT JOIN Song s ON s.AlbumId = a.AlbumId;
    SELECT a.Title, s.Title FROM Song s LEFT JOIN Album a ON s.AlbumId = a.AlbumId;
    ```
1. Using `SELECT` and `LEFT JOIN`, write a query that displays the song title, the song duration, the album label, and the genre name for every song.
1. Using a `WHERE` clause, modify the previous query to only show the information for songs that have a duration of 250 or greater.
1. Write a `SELECT` statement to display how many songs exist for each album. You'll need to use the `COUNT()` function and the `GROUP BY` keyword sequence.
1. Write a `SELECT` statement to display how many songs exist for each artist. You'll need to use the `COUNT()` function and the `GROUP BY` keyword sequence.
1. Write a `SELECT` statement to display how many songs exist for each genre. You'll need to use the `COUNT()` function and the `GROUP BY` keyword sequence.
1. Write a `SELECT` statement to display how many artists exist for each genre. You'll need to use the `COUNT()` function and the `GROUP BY` keyword sequence.
1. Using `MAX()` function, write a select statement to find the album with the longest duration. The result should display the album title and the duration.
1. Using `MAX()` function, write a select statement to find the song with the longest duration. The result should display the song title and the duration.
1. Modify the previous query to also display the title of the album.

## SQL Challenge

You can limit the results of a query using the `LIMIT` keyword.

```sql
SELECT Title
FROM Song
LIMIT 1
```

This will only return the first row of the results.

Your challenge is to write a query to answer the following questions from the sales team.

1. Which album has the most songs?
1. Which genre has been assigned to the most songs?
1. Which record label has released the most albums?

To accomplish this, you will need to use the `MAX()` aggregation function, the `GROUP BY` clause, the `ORDER BY` clause, and the `LIMIT` keyword.

## Additional Practice

🦊 🦏 🐴  🐼

Do tutorials 1-10 on [SQL Zoo](https://sqlzoo.net/)

🐷 🐏 🐰 🐧

