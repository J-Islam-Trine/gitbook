# রাউট হ্যান্ডলারের রেসপন্স \(Response from Route Handlers\)

### রাউট হ্যান্ডলার

রাউট হ্যান্ডলার হচ্ছে একটা কলব্যাক ফাংশন যার মাধ্যমে রিকুয়েস্ট রিসিভ আর রেসপন্স সেন্ড করা যায়\(সাথে ডেটা, যদি থাকে\)।

`app.get('/',` **`(request, response) => {`** 

**`//....`** 

**`}`**`)`

### রেসপন্স হ্যান্ডল করা

#### text বা html রেসপন্স

```javascript
app.get('/', (request, response) => {
    //...
    response.send('some text!')
})
```

#### খালি রেসপন্স

```javascript
app.get('/', (request, response) => {
    //...
    response.end();
})
```

#### শুধু স্ট্যাটাস কোড

```javascript
app.get('/', (request, response) => {
    //...
    response.status(404).end();
})
```

#### json রেসপন্স

```javascript
//...
app.use(express.json())
//...
app.get('/', (request, response) => {
    //...
    response.status(404).json({error: 'object not found.'});
})
```

