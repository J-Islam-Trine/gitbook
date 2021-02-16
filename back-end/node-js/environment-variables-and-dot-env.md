# এনভায়রনমেন্ট ভ্যারিয়েবল\(Environment Variables & Dot Env\)

### ইনস্টলেশন

```text
npm install --save dotenv
```

### সেটআপ

অ্যাপের একদম শুরুতে সার্ভার ফাইলে।

```text
require('dotenv').config()
```

### 

### .env ফাইল

মূল ফোল্ডারে .env নামের একটা ফাইল তৈরি করি।

### এনভায়রনমেন্ট ভ্যারিয়েবল স্টোর করা

.env ফাইলে ভ্যারিয়েবলগুলো রাখা হবে **NAME=VALUE** ফরম্যাটে। যেমন - 

```text
DB_HOST=localhost
DB_USER=root
```

### এনভায়রনমেন্ট ভ্যারিয়েবল ব্যবহার করা

```text
db.connect({
  host: process.env.DB_HOST,
  username: process.env.DB_USER,
  password: process.env.DB_PASS
})
```



