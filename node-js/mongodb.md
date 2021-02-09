# মঙ্গোডিবি \(MongoDB\)

### মঙ্গোডিবি সেটআপ

{% embed url="https://docs.atlas.mongodb.com/getting-started/" %}

### কানেকশন স্ট্রিং 

.env ফাইলের মধ্যে যাবে

```text
DB_URL=mongodb+srv://:<password>@cluster0.gpsrn.mongodb.net/?retryWrites=true
```

এবারে আমাদের অ্যাপে process.env.DB\_URL থেকে ভ্যালুটা নেয়া যাবে।

### ডাটাবেজের সাথে কানেক্ট করা

```javascript
mongoose.connect(config.DB_URL, {useNewUrlParser: true, useUnifiedTopology: true})
```

### ডিসকানেক্ট করা

```text
mongoose.connection.close();
```

**অনেক ক্ষেত্রে কোন একটা এন্ডপয়েন্টের জন্য রিকুয়েস্ট-রেসপনস শেষ করার পর কানেকশন ক্লোজ করে দিলে এরপরে অন্য কোন এন্ডপয়েন্টে পাঠানো রিকুয়েস্টের সময় ডাটাবেজের সাথে কানেক্ট নাও হতে পারে।**

