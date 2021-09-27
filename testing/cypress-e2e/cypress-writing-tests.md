# Cypress-এ টেস্ট লেখা \(Writing tests\)

Cypress একচুয়ালি Mocha ইউজ করে বলে টেস্টের স্ট্রাকচারটা একদম jest/mocha দিয়ে লেখা টেস্টের মতনই।

### টেস্টের স্ট্রাকচার

```javascript
describe('The quintential App', function() {
    //টেস্টগুলো এখানে লিখতে হবে
    it('name of the test', function() {
            //টেস্ট
    })

})
```

{% hint style="danger" %}
> ### চাইলে arrow function দিয়ে টেস্ট লিখতে পারেন, তবে কখন কী হয়ে যাবে সেইটার গ্র্যান্টি আমি দিতে পারবো না।

### Mocha
{% endhint %}

### টেস্টের শুরুতে বার বার করতে হয় এমন কিছুর জন্য beforeEach ব্যবহার

যেহেতু Cypress-এ Mocha ব্যবহার করা হয়, তাই আমরা চাইলে Mocha/Jest testing-এর মতই একটা beforeEach ব্লক ব্যবহার করতে পারি।

```javascript
describe('The quintential App', function() {
    //শুরুতে বার বার করতে হয় 
    //এমন কাজগুলোর জন্য beforeEach ব্লকের ব্যবহার 
    beforeEach(function(){
        //...
        //...
    })

    //Test1
    //Test2
})
```



