# ডাটা টাইপস \(Data Types\)

## VARCHAR

সর্বোচ্চ ২৫৫ অক্ষর। VARCHAR\(n\) দিয়ে ডিক্লেয়ার করা যায় যেখানে n এর ভ্যালু হচ্ছে সর্বোচ্চ অক্ষর সংখ্যা।

## INT

পূর্ণসংখ্যা। 

## CHAR

যদি কোন কলামের সবগুলো ফিল্ডের ভ্যালু একই দৈর্ঘ্যের হয় \(যেমন, M/F\(Male/Female\) বা ফোন নম্বর; তাহলে CHAR\(n\) ব্যবহার করা যেতে পারে। এটা VARCHAR-এর তুলনায় খানিকটা ফাস্ট।

## DECIMAL

DECIMAL\(m,n\) দিয়ে দশমিক সহ মান নির্দেশ করে, যেখানে m হচ্ছে সর্বোচ্চ অংকের সংখ্যা আর n হচ্ছে দশমিকের পরে কতগুলো অংক থাকবে তার সংখ্যা।

## DATE

তারিখ, YYYY-MM-DD ফরম্যাটে।

## TIME

সময় HH:MM:SS আকারে।

## DATETIME

YYYY-MM-DD HH:MM:SS আকারে দিন ও সময়।

## TIMESTAMP

TIMESTAMP দেখতে DATETIME-এর মত হলেও এদের কাজে পার্থক্য আছে। TIMESTAMP ব্যবহার করা হয় বর্তমানে হওয়া কোন কিছুর সময়কাল সেভ করার জন্য। যেমন, এখন তোলা ছবি। আর যদি আগের কোন ডাটা, যেমন জন্ম তারিখ ইনসার্ট করতে হয়, সেটার জন্য উপযুক্ত হচ্ছে DATETIME.

যেমন, নীচের মত করে timestamp ব্যবহার করা যায়,

```sql
CREATE TABLE some_name (
        userID INT NOT NULL AUTO_INCREMENT,
        ...
        ...
        ...
        ...
        created_at TIMESTAMP DEFAULT NOW() ON UPDATE CURRENT_TIMESTAMP
);
```

\q







 





