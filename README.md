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

## 2.) Anonymize data with Athena using hashing
    CREATE table "tcp-ds-anonymized".customer
    WITH (format='parquet',external_location = 's3://tcp-ds-eu-west-1-1tb-anonymised/2/customer_parquet/')
    AS SELECT       
         sha256(to_utf8(cast(c_customer_sk AS varchar))) AS c_customer_sk_anonym,
         sha256(to_utf8(cast(c_customer_id AS varchar))) AS c_customer_id_anonym,
         sha256(to_utf8(cast(c_first_name AS varchar))) AS c_first_name_anonym,
         sha256(to_utf8(cast(c_last_name AS varchar))) AS c_last_name_anonym,
         c_current_cdemo_sk,
         c_current_hdemo_sk,
         c_first_shipto_date_sk,
         c_first_sales_date_sk,
         c_salutation,
         c_preferred_cust_flag,
         c_current_addr_sk,
         c_birth_day,
         c_birth_month,
         c_birth_year,
         c_birth_country,
         c_last_review_date_sk
    FROM customer

## 3.) Substring masking

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
