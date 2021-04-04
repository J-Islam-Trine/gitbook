---
description: DISTINCT
---

# Bশোধনাগার \(The Refinery\)

### DISTINCT

কোন ভ্যালু একাধিক বার থাকলে শুধু মাত্র প্রথম বারের ভ্যালুটা দিবে।

```sql
SELECT DISTNICT column_name FROM some_table;
```

### LIMIT

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











