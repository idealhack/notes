# SQL


- [[MySQL]]
- [[Time series database]]


## Task

### JOIN

    select a.name, b.id, b.name
    from db_a.tb_a as a join db_b.tb_b as b
    where a.name = "test" and a.b_id = b.id
