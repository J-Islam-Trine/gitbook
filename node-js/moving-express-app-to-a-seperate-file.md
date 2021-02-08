# এক্সপ্রেস অ্যাপ আলাদা করে ফেলা \(Moving express app\(\) to a seperate file\)

### কেন?

* টেস্টিং-এর SuperTest আর্গুমেন্ট হিসেবে express app নিয়ে থাকে। সেটাকে আলাদা না করলে তা পাস করা যাবে না।

#### আলাদা ফাইলে এক্সপ্রেস অ্যাপ

app.js ফাইলের ভেতরে - 

```text
const express = require('express');
const app = express();

module.exports = app;
```

#### এক্সপ্রেস অ্যাপ সার্ভার ফাইলে নিয়ে আসা

```text
const app = require('./app')
```

