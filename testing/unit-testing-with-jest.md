# ইউনিট টেস্টিং\(Unit Testing With Jest\)

### Jest ইনস্টলেশন

```text
npm install --save-dev jest
```

### টেস্ট রান কমান্ড

{% code title="package.json" %}
```javascript
  "scripts": 
  {
    "tests": "jest --verbose"
  }
```
{% endcode %}

### টেস্ট রান করা

```javascript
nom run tests
```

### টেস্ট এনভায়রনমেন্ট সেট করা

{% code title="package.json" %}
```javascript
"jest" : {
    "testEnvironment: "Node"
}
```
{% endcode %}

### টেস্ট এক্সাম্পল ফাংশন

উদাহরণ হিসেবে নিচের ফাংশনটার কথাই ধরা যাক।

{% code title="multiply.js" %}
```javascript
const multiply = (x,y) => {
    return x*y;
}
```
{% endcode %}

প্রথমেই ফাংশনটাকে এক্সপোর্ট করে নিই - 

{% code title="multiply.js" %}
```javascript
module.exports = { multiply, }
```
{% endcode %}

{% hint style="info" %}
**টেস্টগুলো সব সময় .test.js নামের এক্সটেনশনওয়ালা ফাইলের মধ্যে থাকবে। যেমন - tests\_for\_multiply.test.js**
{% endhint %}

### টেস্ট ফাইলে ফাংশন ইমপোর্ট করা

{% code title="tests\_for\_multiply.test.js" %}
```text
const multiply = require('multiply.js').multiply
```
{% endcode %}

### টেস্ট গ্রুপের নাম এড করা

describe\(\) দিয়ে টেস্টের নাম দেয়া যায় -

{% code title="tests\_for\_multiply.test.js" %}
```javascript
describe('multiply', ()=>{

})
```
{% endcode %}

### আলাদা আলাদা টেস্টের নাম

{% code title="tests\_for\_multiply.test.js" %}
```javascript
describe('multiply', ()=> {
        test('two time three is six', ()=> {

        })
})
```
{% endcode %}

### টেস্ট করা

{% code title="tests\_for\_multiply.test.js" %}
```javascript
describe('multiply', ()=> {
        test('two times three is six', ()=> {
                const result = multiply(2,3);
                expect(result).toBe(6);
        })
})
```
{% endcode %}

expect\(\) ফাংশন multiply\(\)-কে কল করে পাওয়া ভ্যালুর মান toBe\(\)-তে দেয়া মানের সমান হবে ধরে নিচ্ছে।

### টেস্ট রান করা \(সব টেস্ট\)

```text
npm run tests
```

### আরো টেস্ট ফাংশন

চাইলে একই ফাইলে একাধিক ফাংশন এড করা যাবে। তবে সেগুলোর জন্যে টেস্ট ফাইল আলাদা রাখাই ভালো।

### একটা মাত্র টেস্ট রান করা

describe\(\) ফাংশন লেখার সময় দেয়া নাম দিয়ে একটা মাত্র টেস্ট রান করানো যায় -

```text
npm run tests -- -t 'multiply'
```

আবার চাইলে একটা নির্দিষ্ট টেস্টও রান করানো যায় -

```javascript
npm run tests -- -t 'two times three is six'
```

সেম কমান্ড আবার তা 'times' শব্দটা যতগুলা টেস্টের নামে আছে, সেই সবগুলা টেস্ট রান করবে

```javascript
npm run tests -- -t 'times'
```

### toBe বনাম toEqual

টেস্ট করার ফাংশন যদি আউটপুট দেয় নাম্বার/স্ট্রিং তাহলে toBe\(\) দিয়েই টেস্ট করা যাবে। অবজেক্ট/অ্যারে হলে toEqual\(\) ব্যবহার করতে হবে -

{% code title="tests\_for\_multiply.test.js" %}
```javascript
describe('Favorite Blog', () => {
    const zeroBlogs = [];
    test('zero blog, no favorite', ()=> {
        expect(favoriteBlog(zeroBlogs)).toEqual({ });
    });
});
```
{% endcode %}

কারণ অবজেক্টের ক্ষেত্রে ব্যাপারটা একই বইয়ের দুইটা কপির মতন। দুইটা একই বই, কিন্তু আলাদা আলাদা বস্তু।

