# আউটপুট ফরম্যাট করা \(Formatting The Output\)

## রিনেম \(Rename\)

### AS

```sql
SELECT column_1 AS 'alias_name' FROM table_name;
```

## স্ট্রিং অপারেশন \(String Operations\)

### CONCAT

```sql
SELECT CONCAT (column_1, ' ', column_4) 
AS 'alias_name' FROM table_name;
```

### CONCAT\_WS

```sql
SELECT CONCAT_WS(' ', column1, column2, column3, column_4) 
AS 'alias_name' FROM table_name;
```

### SUBSTRING

```sql
SELECT SUBSTRING(column_name, start, end) 
AS 'alias_name' FROM table_name;
```

এখানে ১ থেকে শুরু হবে।

```sql
SELECT SUBSTRING(column_name, -count) 
AS 'alias_name' FROM table_name;
```

শেষ থেকে শুরু হয়ে count সংখ্যক অক্ষর পর্যন্ত সাবস্ট্রিং দিবে।



