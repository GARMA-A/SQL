## DDL (DATA DEFINITION LANGUAGE)


```sql
CREATE TABLE person ( -- you can write CREATE TABLE IF NOT EXISTS person (
    id SERIAL NOT NULL,
    person_name VARCHAR(255) NOT NULL,
    birth_date DATE NOT NULL,
    CONSTRAINT pk_person_id PRIMARY KEY (id)
);

ALTER TABLE person ADD COLUMN email VARCHAR(255);
ALTER TABLE person DROP COLUMN email;
ALTER TABLE person RENAME TO individual;
ALTER TABLE person MODIFY COLUMN birth_date TIMESTAMP NOT NULL;

DROP TABLE person;
DROP INDEX IF EXISTS idx_person_name;
DROP VIEW IF EXISTS person_view;
```


