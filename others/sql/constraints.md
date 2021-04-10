# কনস্ট্রেইন্টস \(Constraints\)

### কনস্ট্রেইন্টস \(Constraints\)

বিভিন্ন শর্ত যেগুলো ডাটা ইনসার্ট ও আপডেট ও ডিলিটকে নিয়ন্ত্রণ করে থাকে। 

## NOT NULL

যদি NOT NULL কনস্ট্রেইন্ট দেয়া না থাকে,  তাহলে সে কলামটির ভ্যালু কখনো NULL হবে না।

```sql
CREATE TABLE cats2
  (
    name VARCHAR(100) NOT NULL,
    age INT NOT NULL
  );
```

## DEFAULT

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

## Primary key

Primary Key হচ্ছে টেবিলের প্রতিটা এন্ট্রি/টাপলের জন্য সেই কলাম/এট্রিবিউট যেটা প্রত্যেকটা এন্ট্রির জন্য আলাদা হবে আর NULL হবে না। Primary Key দিয়ে সবগুলো এন্ট্রিকে আলাদা আলাদা ভাবে চিহ্নিত করা যায়। নিচের মত করে এটা ডিফাইন করা যায়।

```sql
CREATE TABLE cats3
  (
    id INT NOT NULL,
    name VARCHAR(20) DEFAULT 'no name provided',
    age INT DEFAULT 99,
    PRIMARY KEY (name, age)
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

## FOREIGN KEY

একটা টেবিল/এনটিটি সেটে অন্য আরেকটা টেবিলের Primary key-কে নির্দেশ করে। Foreign Key হিসেবে অন্য টেবিলের Primary Key যুক্ত করলে এমন কোন মান ইনসার্ট করা যায় না, যেটা foreign key যে টেবিলে রয়েছে তার সেই কলামটিতে নেই।

```sql
CREATE TABLE some_table (
id INT NOT NULL AUTO_INCREMENT,
...
...,
column4 INT,
PRIMARY KEY (id),
FOREIGN KEY (column4) 
REFERENCES foreign_table(PRIMARY_KEY_in_foreign_table)
);
```

## AUTO\_INCREMENT

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

## UNIQUE

কলামের প্রতিটা ভ্যালু ভিন্ন হবে।

```sql
CREATE TABLE some_table (
        ...,
        ...
        column_name UNIQUE,
        ...
)
```

## CHECK

চেক দিয়ে সেই টেবিলের কলামের জন্য নানা শর্ত বেঁধে দেয়া যায়। 

```sql
CREATE TABLE some_table (
                column1 INT,
                column2 INT,
                ...,
                ...,
                CONSTRAINT `cant be equal` 
                                CHECK(column1 <> column2)


)
```

এখানে cant be equal নামের একটা কনস্ট্রেইন্ট দেয়া হয়েছে যেটা বলছে যে, column1 এর যে কোন ফিল্ডের ভ্যালু column2এর ফিল্ডের ভ্যালুর চেয়ে বড় বা ছোট হতে পারবে তবে সমান হতে পারবে না।







\_\_



