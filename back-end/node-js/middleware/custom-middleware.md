# কাস্টম মিডলওয়্যার\(Custom MiddleWare\)

### কাস্টম মিডলওয়্যার

```javascript
const ack = (req, res, next) => {
    console.log('logged!');
    next()
}
```

next\(\) পরের মিডলওয়্যারকে কল করে।

### কাস্টম মিডলওয়্যার ব্যবহার করা

```javascript
app.use(ack);
```

### এরর হ্যান্ডলার

```javascript
const errorHandler = (error, request, response, next) => {

    //...

  next(error)
}
```

### ভুল এন্ডপয়েন্টে করা রিকুয়েস্ট হ্যান্ডলার

```javascript
const unknownEndpoint = (request, response) => {
  response.status(404).send({ error: 'unknown endpoint' })
}
```

**এই মিডলওয়্যার সব সময় এরর হ্যান্ডলারের আগে দিয়ে এড করতে হবে।**

## **কোড রেফারেন্স**

{% page-ref page="../../../undefined/jwt-jwt-token-extractor-middleware.md" %}



