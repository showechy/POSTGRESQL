# راهنمای جامع برای کار با PostgreSQL

## 1. اتصال به دیتابیس PostgreSQL

برای اتصال به پایگاه داده PostgreSQL از خط فرمان، از دستور زیر استفاده کنید:

```bash
psql -h <host> -U <username> -d <database>
```

- `<host>`: آدرس سرور PostgreSQL (برای اتصال محلی، `localhost` را وارد کنید).
- `<username>`: نام کاربری PostgreSQL.
- `<database>`: نام پایگاه داده‌ای که می‌خواهید به آن متصل شوید.

**مثال:**

```bash
psql -h localhost -U postgres -d mydb
```

## 2. مشاهده جداول

برای مشاهده لیست جداول در پایگاه داده فعلی، از دستور زیر استفاده کنید:

```sql
\dt
```

## 3. حذف دیتابیس خاص

برای حذف پایگاه داده، از دستور زیر استفاده کنید:

```sql
DROP DATABASE <database_name>;
```

**مثال:**

```sql
DROP DATABASE mydb;
```

## 4. مشاهده رکوردهای جداول

برای مشاهده رکوردهای یک جدول خاص، از دستور زیر استفاده کنید:

```sql
SELECT * FROM <table_name>;
```

**مثال:**

```sql
SELECT * FROM users;
```

## 5. ایجاد یک پایگاه داده جدید

برای ایجاد پایگاه داده جدید، از دستور زیر استفاده کنید:

```sql
CREATE DATABASE <database_name>;
```

**مثال:**

```sql
CREATE DATABASE newdb;
```

## 6. ایجاد یک جدول جدید

برای ایجاد جدول جدید، از دستور زیر استفاده کنید:

```sql
CREATE TABLE <table_name> (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

**مثال:**

```sql
CREATE TABLE employees (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    position VARCHAR(50),
    salary NUMERIC
);
```

## 7. افزودن رکورد به جدول

برای افزودن رکورد به جدول، از دستور زیر استفاده کنید:

```sql
INSERT INTO <table_name> (column1, column2, ...)
VALUES (value1, value2, ...);
```

**مثال:**

```sql
INSERT INTO employees (name, position, salary)
VALUES ('John Doe', 'Developer', 60000);
```

## 8. حذف رکورد از جدول

برای حذف رکورد از جدول، از دستور زیر استفاده کنید:

```sql
DELETE FROM <table_name>
WHERE <condition>;
```

**مثال:**

```sql
DELETE FROM employees
WHERE id = 1;
```

## 9. بروزرسانی رکوردهای جدول

برای بروزرسانی رکوردها، از دستور زیر استفاده کنید:

```sql
UPDATE <table_name>
SET column1 = value1, column2 = value2, ...
WHERE <condition>;
```

**مثال:**

```sql
UPDATE employees
SET salary = 65000
WHERE id = 1;
```
