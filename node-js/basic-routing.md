# বেসিক রাউটিং\(Basic Routing\)

### রাউটগুলোর সাধারণ রুপ

```text
app.METHOD(PATH, HANDLER)
```

### উদাহরণ

```javascript
app.get('/', (request, response) => {
    //....
})
```

### রাউট প্যারামিটারস \(route parameters\)

রাউট প্যারামিটার হচ্ছে পাথের মাধ্যমে পাস করা ভ্যালু।

```javascript
app.get('/users/:id', (request, response) => {
    const id = request.params.id;
})
```

যা পরে **request.params** থেকে একসেস করা যায়।

