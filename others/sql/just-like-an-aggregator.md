---
description: 'COUNT, GROUP BY,'
---

# সমবায়ক সম \(Just Like An Aggregator\)

### COUNT

কতগুলো row আছে তা গণনা করার জন্য - 

```sql
SELECT COUNT(*) FROM table_name;
```

এভাবে যদিও column বলে দেয়া যেতে পারে \* এর জায়গায়, তবে তাতে ফলাফলে কোন পরিবর্তন হবে না। কারণ এতে রিপিটেশন সহ সব কাউন্ট করবে। সেজন্য column এর নামের আগে distinct ব্যবহার করতে হবে।

### GROUP BY

GROUP BY কলামের উপর ভিত্তি করে টাপলগুলোকে এক গ্রুপে আনে, তবে শুধু মাত্র সেই গ্রুপের প্রথম row টা দেখায়। অনেকটা ট্যাবড লিস্টের মত। 

```sql
SELECT title, pages
FROM books
GROUP BY author;
```

### MAX/MIN

MAX/MIN কোন একটা কলামের সর্বোচ্চ/সর্বনিম্ন মানটা দেয়।

```sql
SELECT MAX(pages) AS "Maximum Page"
FROM books;
```

MIN-ও একই ভাবে ব্যবহার করা যায়। 

তবে সঙ্গত কারণেই নিচের কুয়েরিটা ভুল ফলাফল দিবে।

```sql
SELECT MAX(pages) AS "Maximum Page", title
FROM books;
```

কারণ হচ্ছে MAX\(pages\) এর সাথে title এর কোন লিংক নাই যে সে নিজে নিজেই তার title বের করবে। এই ক্ষেত্রে ORDER BY ব্যবহার করা যেতে পারে

### SUM

```sql
SELECT SUM(pages) AS "Maximum Page"
FROM books;
```

### AVERAGE

```sql
SELECT AVG(pages) AS "Maximum Page"
FROM books;
```















