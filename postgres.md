### Command to work with PostgreSQL

Get query select and convert to .csv file:
```
psql -h localhost finops -p 5432 -U be_backend_postgres -c "Copy (select * from trip_finance_details where payment_method=1 order by create_time desc) To STDOUT With CSV HEADER DELIMITER ',';" > /tmp/output.csv
```
