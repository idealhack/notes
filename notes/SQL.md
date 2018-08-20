# SQL

## Overview

- [SQL - 维基百科](https://zh.wikipedia.org/wiki/SQL)

## Databases

- [[MySQL]]
- [[PostgreSQL]]

## Tasks

Drop database:

    DROP database db_name;

Alter tables:

    ALTER TABLE table_name
    ADD COLUMN new_column_name data_type;
    
    ALTER TABLE table_name
    RENAME old_column_name TO new_column_name;

Create:

    INSERT INTO "users" (last_name, first_name)
    VALUES ('Alice', ''), ('Bob', '');

Read:

    SELECT *
    FROM users
    WHERE id = 1;

Update:

    UPDATE users
    SET telegram_name = 'idealhack'
    WHERE telegram_id = 34804908;

Delete:

    DELETE FROM torrents
    WHERE id = 166;

IN operator:

    DELETE FROM torrents WHERE id NOT IN ( SELECT torrent_id FROM user_torrents );

JOIN operator:

    SELECT a.name, b.id, b.name
    FROM db_a.tb_a as a JOIN db_b.tb_b as b
    WHERE a.name = "test" AND a.b_id = b.id;

## Tools

- [Franchise: a sql notebook](https://franchise.cloud/)
