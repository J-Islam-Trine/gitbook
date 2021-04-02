# কনস্ট্রেইন্টস \(Constraints\)

### কনস্ট্রেইন্টস \(Constraints\)

বিভিন্ন শর্ত যেগুলো ডাটা ইনসার্ট ও আপডেট ও ডিলিটকে নিয়ন্ত্রণ করে থাকে। 

### NOT NULL

যদি NOT NULL কনস্ট্রেইন্ট দেয়া না থাকে,  তাহলে সে কলামটির ভ্যালু কখনো NULL হবে না।

```sql
CREATE TABLE cats2
  (
    name VARCHAR(100) NOT NULL,
    age INT NOT NULL
  );
```

### DEFAULT

DEFAULT দিয়ে কলামের জন্য ডিফল্ট ভ্যালু স্পেসিফাই করা যায়।

```sql
CREATE TABLE cats3
  (
    name VARCHAR(20) DEFAULT 'no name provided',
    age INT DEFAULT 99
  );
```

{% hint style="info" %}
_কোন কলামের জন্য যদি ভ্যালু না দেয়া হয়, তাইলে NOT NULL ও DEFAULT-এর উপর ভিত্তি করে নিচের  ভ্যালুগুলোর একটি বসবেঃ_

NOT NULL নেই + DEFAULT নেই = NULL

NOT NULL নেই + DEFAULT আছে = DEFAULT ভ্যালু

NOT NULL আছে + DEFAULT নেই = "   " / 0

NOT NULL আছে + DEFAULT আছে = DEFAULT ভ্যালু \(তবে কোন ভাবেই NULL ভ্যালু নয়\)
{% endhint %}

### Primary key

Primary Key হচ্ছে টেবিলের প্রতিটা এন্ট্রি/টাপলের জন্য সেই কলাম/এট্রিবিউট যেটা প্রত্যেকটা এন্ট্রির জন্য আলাদা হবে আর NULL হবে না। Primary Key দিয়ে সবগুলো এন্ট্রিকে আলাদা আলাদা ভাবে চিহ্নিত করা যায়। নিচের মত করে এটা ডিফাইন করা যায়।

```sql
CREATE TABLE cats3
  (
    id INT NOT NULL,
    name VARCHAR(20) DEFAULT 'no name provided',
    age INT DEFAULT 99,
    PRIMARY KEY (id)
  );
```

অথবা

```sql
CREATE TABLE cats3
  (
    id INT NOT NULL PRIMARY KEY,
    name VARCHAR(20) DEFAULT 'no name provided',
    age INT DEFAULT 99
  );
```

একাধিক কলাম/এট্রিবিউট Primary Key হতেই পারে।

### AUTO\_INCREMENT

Primary Key এর ক্ষেত্রে প্রতিটা টাপলের জন্য সেটার ভ্যালু ইউনিক হলেও ইউজার ইনপুটের মাধ্যমে ইউনিক ভ্যালু মেইনটেইন করাটা টাফ। সেজন্য Primary Key এর ক্ষেত্রে AUTO\_INCREMENT কনস্ট্রেইন্ট যুক্ত করা থাকে, যেটা এই কলামের ভ্যালু প্রতিটির জন্য এক করে বৃদ্ধি করে।

```sql
CREATE TABLE cats3
  (
    id INT NOT NULL AUTO_INCREMENT,
    name VARCHAR(20) DEFAULT 'no name provided',
    age INT DEFAULT 99,
    PRIMARY KEY (id)
  );
```





\_\_



