# PostgreSQL

## Overview

- [PostgreSQL: The world's most advanced open source database](https://www.postgresql.org/)
- [PostgreSQL: Documentation: 10: PostgreSQL 10.1 Documentation](https://www.postgresql.org/docs/10/static/index.html)

## Common Tasks

Dump tables:

    pg_dump -t 'aschema.atable' --schema-only database-name

Alter tables:

    ALTER TABLE table_name
    ADD COLUMN new_column_name data_type;
    
    ALTER TABLE table_name
    RENAME old_column_name TO new_column_name;

Create:

    INSERT INTO "users" (last_name, first_name)
    VALUES ('Alice', ''), ('Bob', '')
    RETURNING *;

Read:

    SELECT *
    FROM users
    WHERE id = 1;

Update:

    UPDATE users
    SET telegram_name = 'idealhack'
    WHERE telegram_id = 34804908
    RETURNING *;

Delete:

    DELETE FROM torrents
    WHERE id = 166
    RETURNING *;

Update:

    UPDATE users
    SET telegram_name = 'idealhack'
    WHERE telegram_id = 34804908
    RETURNING *;

IN operator:

    DELETE FROM torrents WHERE id NOT IN ( SELECT torrent_id FROM user_torrents );

## Resources

- [dhamaniasad/awesome-postgres: A curated list of awesome PostgreSQL software, libraries, tools and resources, inspired by awesome-mysql](https://github.com/dhamaniasad/awesome-postgres)
- [liuyuanyuan/fantastic-postgres: Documents and tools for open source database - PostgreSQL.](https://github.com/liuyuanyuan/fantastic-postgres)
