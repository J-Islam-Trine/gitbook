# বেসিক নোড সার্ভার \(Basic Node Server\)

#### http মডিউল যুক্ত করা

```javascript
const http = require('http');
```

#### সার্ভার অ্যাপ

```javascript
const app = (request, response) => 
{
    response.writeHead(200, { 'Content-Type' : 'text/plain' });
    response.send('hello world');
}

const server = http.createServer(app)
```

writeHead\(\) ফাংশনটি 200 OK স্ট্যাটাস কোড দিবে আর পাঠানো কন্টেন্টের টাইপ বলে দিবে।

```javascript
server.listen(3001, () => {
    console.log(`listening for connections at port 3001`);
})
```

এবারে অ্যাপটি 3001 পোর্টে চালু হয়ে যাবে।\



#### সার্ভার রান করা

প্রজেক্ট ফোল্ডারে টার্মিনাল থেকে রান করতে হবে -

```text
node index.js
```

থামানোর জন্য ctrl+c চাপতে হবে।

