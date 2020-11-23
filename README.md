# Athena Quick Query Reference

## Date & Timestamp

 ## 1.) Timestamp string to date
    select cast(from_iso8601_timestamp('2015-01-04T00:00:01.206255Z') as date);

## 2.) Extract date, month, year, hour , minute, second

     select year(cast(from_iso8601_timestamp('2015-01-04T00:00:01.206255Z') as date));

     select month(cast(from_iso8601_timestamp('2015-01-04T00:00:01.206255Z') as date));

     select day(cast(from_iso8601_timestamp('2015-01-04T00:00:01.206255Z') as date));

     select hour(cast(from_iso8601_timestamp('2015-01-04T00:00:01.206255Z') as date));

     select minute(cast(from_iso8601_timestamp('2015-01-04T00:00:01.206255Z') as date));

     select second(cast(from_iso8601_timestamp('2015-01-04T00:00:01.206255Z') as date));

---
## Strings

 ## 1.) Substring
    SELECT substr('AWS is best platform for Builder',1,3);
---

## Condition

## 1.) CASE
    SELECT 1,
       CASE 1
           WHEN 1 THEN 'one'
           WHEN 2 THEN 'two'
           ELSE 'many'
       END;
       
---       

## Reference

https://docs.aws.amazon.com/athena/latest/ug/presto-functions.html

https://prestodb.io/docs/0.217/functions/datetime.html
