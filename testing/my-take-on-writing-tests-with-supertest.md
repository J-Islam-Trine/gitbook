# টেস্ট লেখা নিয়ে কিছু পয়েন্ট \(My take on writing tests with Supertest\)

টেস্টের একদম শুরুতে কিছু করতে হলে \(ডাটাবেজ সেটআপ বা এমন কিছু\), সেটার জন্য সব টেস্টের আগে beforeAll\(\) ইউজ করতে হবে।

beforeAll\(\) -এ ডাটাবেজ কানেক্ট না করাই ভালো, তাতে করে টেস্ট হতে সময় লাগে বেশি \(9টা টেস্টের একটি স্যুট beforeAll\(\)-এ ডাটাবেজ কানেক্ট না করা থাকলে সময় নিয়েছে 10 সেকেন্ড, যেখানে beforeAll\(\)-এ কানেক্ট করা হলে তা নিয়েছে 12 সে্কেন্ড\)।

উপরের মত হওয়ার কারণ সম্পর্কে একটা হিন্ট পাওয়া যায় Supertest-এর ডকুমেন্টেশনে -

{% hint style="info" %}
 _You may pass an `http.Server`, or a `Function` to `request()` - if the server is not already listening for connections then it is bound to an ephemeral port for you so there is no need to keep track of ports._
{% endhint %}

টেস্ট লেখার সময় যে Asynchronous কলের রেজাল্ট আমরা test করবো, সেটা দুই ভাবে লেখা যেতে পারে। 

```javascript
//First Way
const resp = await api.
    get('/api/blogs');
    expect(resp.status).toBe(400)
    
//second way
await api.
get('/api/blogs')
expect(400)
```

দুটোতে টেস্টে কতটুকু সময় লাগবে, সেটাতে সাবস্ট্যানশিয়াল হলেও পার্থক্য হবে।

সবশেষে, সব টেস্ত রান করে ফেলার পর কিছু করতে হলে afterAll\(\) ব্যবহার করা যেতে পারে।

## কোড রেফারেন্স

{% page-ref page="../undefined/a-complete-test-suite.md" %}



