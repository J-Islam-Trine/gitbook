---
description: 'DISTINCT, LIMIT, BETWEEN, NOT BETWEEN'
---

# Bশোধনাগার \(The Refinery\)

## DISTINCT

কোন ভ্যালু একাধিক বার থাকলে শুধু মাত্র প্রথম বারের ভ্যালুটা দিবে।

```sql
SELECT DISTNICT column_name FROM some_table;
```

## LIMIT

```sql
SELECT column_name, ....
FROM some_table
LIMIT n;
```

প্রথম n সংখ্যক ফলাফল  দিবে শুধু মাত্র।

```sql
SELECT column_name, ....
FROM some_table
LIMIT lower_bound, count;
```

lower bound থেকে নিয়ে count সংখ্যক পর্যন্ত ফলাফল দিবে। এখানে অ্যারে-এর মত 0 থেকে গণনা শুরু হবে। মানে প্রথম টাপল হচ্ছে 0।

## BETWEEN/NOT BETWEEN

### BETWEEN

একটা রেঞ্জের মধ্যে থাকা ভ্যালু দিবে।

```sql
SELECT something
FROM some_table
WHERE some_value 
BETWEEN uppeer AND lower;
```

### NOT BETWEEN

```sql
SELECT something
FROM some_table
WHERE some_value 
NOT BETWEEN uppeer AND lower;
```

{% hint style="warning" %}
BETWEEN/NOT BETWEEN ব্যবহার করা সময় VARCHAR ডেটকে DATETIME-এ কনভার্ট করে নেয়াই ভালো।

CAST\("01-01-2001" AS DATETIME\);
{% endhint %}

## IN/NOT IN

### IN

কিছু ভ্যালুর সাথে তুলনা করে যেটির সাথে মিলে যাবে সেটার জন্য ফলাফল দিবে।

```sql
SELECT title
FROM books
WHERE released_year IN (2003, 2010, 2014);
```

NOT IN-এর ক্ষেত্রে উল্টোটা হবে।

```sql
SELECT title
FROM books
WHERE released_year NOT IN (2003, 2010, 2014);
```









