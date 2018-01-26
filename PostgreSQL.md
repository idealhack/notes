# PostgreSQL

## Overview

- [PostgreSQL: The world's most advanced open source database](https://www.postgresql.org/)

## Common Tasks

Dump tables:

    pg_dump -t 'aschema.atable' --schema-only database-name

Alter tables:

    ALTER TABLE table_name
    ADD COLUMN new_column_name data_type;

Insert:

    INSERT INTO "users" (last_name, first_name)
    VALUES ('Alice', ''), ('Bob', '')
    RETURNING *

## Resources

- [dhamaniasad/awesome-postgres: A curated list of awesome PostgreSQL software, libraries, tools and resources, inspired by awesome-mysql](https://github.com/dhamaniasad/awesome-postgres)
- [liuyuanyuan/fantastic-postgres: Documents and tools for open source database - PostgreSQL.](https://github.com/liuyuanyuan/fantastic-postgres)
