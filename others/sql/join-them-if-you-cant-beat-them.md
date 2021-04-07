# জয়েন \(Join \(them, if you can't beat them\)\)

## কার্টেশিয়ান জয়েন

দুটো টেবিলের মধ্যেকার কার্টেশিয়ান জয়েনের ফলাফল হচ্ছে প্রতিটা টেবিলের সবগুলো টাপলের সাথে অন্য টেবিলের সব টাপলের কার্টেশিয়ান গুণের ফলাফল।

```sql
SELECT * FROM table1, table2;
```

কার্টেশিয়ান জয়েন এই ফর্মে খুব একটা কাজের না।

## Natural Join

ধরি, table2-তে foreign key আছে tab2\_id, যা রেফার করছে table1-এর idকে।

তাহলে

```sql
SELECT * FROM table1, table2
WHERE foreign_key = table2.tab2_id;
```

{% hint style="danger" %}
**যদি আমি জয়েন-এ ভুল করে ফিরে আসি, তাহলে লক্ষ্য করি যে, এখানে আমি foreign key না লিখে ভুলে table\_name.foreign\_key লিখে ফেলেছি কি না।**
{% endhint %}

## Inner Join

```sql
SELECT *
FROM table1 JOIN table 2 
ON table2.foreign_key = table1.reference_key;
```

যে ধরণে জয়েন অপারেশনে দুইটা টেবিলের যে যে টাপলগুলো ম্যাচ করে না, সেগুলো রাখা হয় না, সেটাকে বলে Inner Join।





