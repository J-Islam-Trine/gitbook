---
description: 'ORDER BY,'
---

# মহান বিন্যাসক \(The Great Formatter\)

### ORDER BY

```sql
SELECT column_name
FROM some_table
ORDER_BY that_column, another_column;
```

যদি descending অর্ডারে \(z-a\) সাজাতে হয়, তাহলে শেষে DESC যুক্ত করতে হবে।

```sql
SELECT column_name
FROM some_table
ORDER_BY that_column DESC;
```

যদি আমরা যে attribute দিয়ে সিলেক্ট করছি, সেগুলোর কোন একটা দিয়েই অর্ডার করি, তাহলে আমরা সেটার ক্রমটাকে অর্ডারে নম্বর হিসেবে দিয়ে দিতে পারি।

```sql
--        1            2            3
SELECT column_name, column_name, column_name
FROM some_table
ORDER_BY that_column 2;
```





