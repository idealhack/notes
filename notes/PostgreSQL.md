# PostgreSQL

## Overview

- [PostgreSQL: The world's most advanced open source database](https://www.postgresql.org/)
- [PostgreSQL中文社区: 世界上功能最强大的开源数据库...](http://www.postgres.cn/index.php/home)

## Common Tasks

Connecting:

    psql -h localhost -U username databasename

See running queries:

    SELECT * FROM pg_stat_activity;
    -- Cancel
    SELECT pg_cancel_backend(PID);
    -- Kill the hard way
    SELECT pg_terminate_backend(PID);

Dump tables:

    pg_dump -t 'aschema.atable' --schema-only database-name

Create users and databases:

    CREATE DATABASE db_name;
    CREATE USER user_name WITH ENCRYPTED PASSWORD 'your_password';
    GRANT ALL PRIVILEGES ON DATABASE db_name TO user_name;

## Resources

- [dhamaniasad/awesome-postgres: A curated list of awesome PostgreSQL software, libraries, tools and resources, inspired by awesome-mysql](https://github.com/dhamaniasad/awesome-postgres)
- [liuyuanyuan/fantastic-postgres: Documents and tools for open source database - PostgreSQL.](https://github.com/liuyuanyuan/fantastic-postgres)
