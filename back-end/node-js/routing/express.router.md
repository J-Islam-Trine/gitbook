# এক্সপ্রেস রাউটার\(express.router\)

* রুট প্রজেক্টে controllers নামে একটা ফোল্ডার বানাই।
* secret.js\(অথবা অন্য নামে\) নামে একটা ফাইল ক্রিয়েট করি।
* ফাইলের মধ্যে express.router ইমপোর্ট করে নিয়ে আসি। 

```javascript
var secretRouter = require('express').Router();
```

* এবারে secretRouter দিয়ে রাউট হ্যান্ডলারগুলো লিখি। আগে যেমন app দিয়ে লিখতাম।

```javascript
secretRouter.get('/', (req, res) => {
    res.send("This is the secret Router");
})
```

* secretRouter এক্সপোর্ট করি।

```javascript
module.exports = secretRouter
```

* app-এ রাউটারটাকে ইমপোর্ট করি।

```javascript
const secretRouter = require('./controllers/secret')
```

* এবারে CORS&gt;static&gt;json&gt;request intercepting middleware -এর পর এটাকে ইউজ করি।

```javascript
app.use('/secret', secretRouter);
```



