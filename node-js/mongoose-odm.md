# মঙ্গোজ\(Mongoose ODM\)

### ইনস্টলেশন

```text
npm install --save mongoose
```

### ইমপোর্ট

```javascript
const mongoose = require('mongoose');
```

### বেসিক স্কিমা

```javascript
const orderSchema = new mongoose.Schema({
    orderNo: Number,
    client: String,
    details: Array,
})
```

### মডেল তৈরি

```javascript
const order = mongoose.model('User', orderSchema);
```

ডাটাবেজে এইটার কালেকশনের নাম হবে Users আর পরেরটা বলছে যে কোন স্কিমা থেকে তা বানানো।

### ডেটা ভ্যালিডেশন

```javascript
const userSchema = new mongoose.Schema({
     username: 
    {
        type: String,
        required: [true, 'user name needed']
    },
    name: 
    {
        type: String
    },
    password: 
    {
        type: String,
        required: true
    }
})
```

