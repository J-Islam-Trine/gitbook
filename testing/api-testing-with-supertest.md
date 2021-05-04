# এপিআই টেস্টিং\(API Testing With Supertest\)

### ইনস্টলেশন

```text
npm install --save-dev supertest
```

Jest

```text
npm install --save-dev jest
```

### testEnvironment ডিফাইন করা

jest.config.js নামে একটা ফাইল তৈরি করতে হবে প্রজেক্টের মূল ফোল্ডারে আর তাতে নিচের অংশটুকু পেস্ট করতে হবে।

```javascript
module.exports = {
    testEnvironment: 'node'
}
```

### টেস্ট ফাইল ক্রিয়েট করা

টেস্টগুলো .test.js এক্সটেনশনের ফাইলের মধ্যে থাকবে, যেমন: **tests\_for\_api.test.js**

### Supertest ইমপোর্ট

tests\_for\_api.test.js ফাইলের মধ্যে Supertest ইমপোর্ট করি।

```javascript
const supertest = require('supertest')
```

### Supertest-কে express app দিয়ে ইনিশিয়ালাইজ করা

```javascript
const app = require('../app)
const api = supertest(app)
```

### বেসিক টেস্ট

```javascript
test('notes are returned as json', async () => {
        await api
        .get('/orders')
        .expect(200)
        .expect('Content-Type', /application\/json/)
})
```

expect\(\) দিয়ে রিটার্নড স্ট্যাটাস আর কন্টেন্ট টাইপ চেকিং যে এই অর্ডারেই করতে হবে, তা নয়। আগে কন্টেন্ট টাইপ আর পরে স্ট্যাটাস চেক করাও সম্ভব।

### টেস্টের পর

```javascript
afterAll(() => {
    mongoose.connection.close();
})
```

কানেকশন না ক্লোজ করলে অপারেশন রান করতে থাকবে টেস্ট রান হয়ে যাওয়ার পরেও।

{% hint style="info" %}
_**এখন আমি Supertest-এর ডকুমেন্টেশনে end\(\) এর সন্ধান পেয়েছি, যেটা টেস্ট শেষ করে কানেকশন ক্লোজ করে দেয়। তাই উপরে ফোর্স কানেকশন ক্লোজটাকে ব্যাড প্র্যাকটিস হিসেবে বিবেচনা করাই ভালো।**_
{% endhint %}

### package.json-এ টেস্ট রান কমান্ড যুক্ত করা

package.json ফাইলটাতে scripts-এর আন্ডারে নিচের ভ্যালুটা এড করি।

```javascript
"test": "cross-env NODE_ENV=test jest --verbose --runInBand"
```

উইন্ডোজ সিস্টেমে এভাবে সরাসরি NODE\_ENV সেট করে দিলে সমস্যা হয়। সেজন্য লাগবে cross-env।

```javascript
npm install --save-dev cross-env
```

### টেস্ট রান করানো

সবগুলো টেস্ট রান করানোর জন্য-

```javascript
npm run test
```

সিঙ্গেল টেস্ট রান করানোর জন্য - 

```text
npm test -- tests/tests_for_api.test.js
```

{% hint style="info" %}
### টেস্টের জন্যে আলাদা ডাটাবেজ

টেস্ট মূল ডাটাবেজের উপর রান না করে আলাদা একটা ডাটাবেজের উপর রান করানোই ভালো।
{% endhint %}

### টেস্ট রান করানোর আগে

কনসিস্টেন্সির জন্য প্রতি বার একটি পার্টিকুলার ডাটাসেটের উপরই টেস্ট করা ভালো। সেজন্য টেস্টের আগে টেস্ট ডেটাবেজের সব এন্ট্রি মুছে দিয়ে নতুন করে টেস্ট ডাটাসেটের ভ্যালু ইনসার্ট করতে হবে। নিচে একটা উদাহরণ দেয়া হলো।

beforeEach\(\) দিয়ে প্রতি বার টেস্ট রান করানোর আগে কিছু রিপিট করা যায়।

মঙ্গোজের মডেলটা ইমপোর্ট  -

```javascript
const Order = require('../models/order')
```

```javascript
beforeEach(async () => {
    await Order.deleteMany({})
    let i =0;
    while (i < dummyOrders.length)
    {
        let newOrder = new Order(dummyOrders[i]);
        await newOrder.save();
        i++;
    }
})
```

**এখানে forEach\(\) কাজ করবে না, কলব্যাক নেয় এমন কোন লুপ দিয়ে এটা করা যাবে না কারণ তখন await অংশটুকু async ফাংশন থেকে আলাদা হয়ে যাবে।**

### হেল্পার ফাংশন

API-এর কোন একটা এন্ডপয়েন্ট চেক করার জন্যে যদি ডাটাবেজ থেকে ডাটা আবার রিট্রিভ করতে হয়, তখন তার জন্য GET এন্ডপয়েন্ট ব্যবহার না করাই ভালো।

## **কোড রেফারেন্স**

\*\*\*\*

