# এক্সপ্রেস ফ্রেমওয়ার্ক ও বেসিক এক্সপ্রেস সার্ভার \(Express Framework and basic server \)

#### এক্সপ্রেস ফ্রেমওয়ার্ক ইনস্টল করা

```text
npm install --save express
```

#### এক্সপ্রেস যুক্ত করার পর

```javascript
const express = require('express');
const app = express();

const server = http.createServer(app)

server.listen(3001, () => {
    console.log(`listening for connections at port 3001`);
})
```



