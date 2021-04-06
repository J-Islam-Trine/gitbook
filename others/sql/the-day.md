# দিন The Day

কিছু বিল্ট-ইন ফাংশন আছে যেগুলো দিয়ে **DATE/TIME/DATETIME** টাইপের ফিল্ড সহজেই ফরম্যাট বা রাইট করা যায়। যেমন:

**CURDATE\(\)** -&gt; আজকের তারিখ।

**CURTIME\(\)** -&gt; এখনকার সময়।

**NOW\(\)** -&gt; তারিখ ও সময়।



এছাড়াও আরো কিছু ফাংশন আছে যা দিয়ে DATE/TIME/DATETIME ভ্যালু থেকে ডেটা বের করা যায়। যেমন - 

YEAR\(\) -&gt; \(DATE/DATETIME\) সাল।

MONTHNAME\(\) -&gt; \(DATE/DATETIME\) মাসের নাম।



সবচেয়ে উপকারী ফাংশনটি হচ্ছে DATE\_FORMAT\(\)। 

```text
DATE_FORMAT(column_name, specifiers);
```

এখানে column\_name হচ্ছে DATETIME টাইপের ফিল্ড আর specifiers হচ্ছে বিশেষ ফরম্যাট যা দিয়ে দিন বা তারিখ বা মাসের নানান ধরণকে নির্দেশ করা যায়, যেমন, %D দিয়ে তারিখের সাফিক্স সহ ফরম্যাট \(21 তারিখের জন্য 21st\) নির্দেশ করা হয়। %M দিয়ে মাসের নাম। 

নিচে একটা উদাহরণ দেয়া হলো যেখানে "21st April, 19xx" ফরম্যাটে আউটপুট ফরম্যাট করা হয়েছে।

```text
DATE_FORMAT(birthday, "%D %M, %Y");
```

**INTERVAL** এর মাধ্যমে DATETIME এর সঙ্গে সময় যোগ বিয়োগ করা যায়।

```text
birthday + INTERVAL 1 MINUTE + INTERVAL 1 MONTH;
```



