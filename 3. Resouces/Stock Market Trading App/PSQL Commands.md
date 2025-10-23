1. Order by Date
		SELECT *
		FROM table_name
		ORDER BY date_column DESC
		LIMIT 5;
2.
drop all tables:-
DO
$$ DECLARE
    r RECORD;
    cnt INT := 0;
BEGIN
    FOR r IN (SELECT tablename FROM pg_tables WHERE schemaname = 'public') LOOP
        EXECUTE 'DROP TABLE IF EXISTS ' || quote_ident(r.tablename) || ' CASCADE';
        cnt := cnt + 1;
        -- Commit every 50 tables to avoid lock exhaustion
        IF cnt % 50 = 0 THEN
            COMMIT;
        END IF;
    END LOOP;
END $$;


### PostgreSQL Command to Describe a Table

The command is:  \d+ table_name



# Remove tables by Name

DO $$
DECLARE
    tbl RECORD;
BEGIN
    FOR tbl IN
        SELECT tablename
        FROM pg_tables
        WHERE schemaname = 'public'
          AND (tablename LIKE 'fs_%' OR tablename LIKE 'prep_%')
    LOOP
        EXECUTE format('DROP TABLE IF EXISTS %I CASCADE;', tbl.tablename);
    END LOOP;
END $$;

### Clear Screen
\! cls 