# Unique - ইউনিক ভ্যালিডেটর

{% hint style="danger" %}
Mongoose-এর স্কিমাতে unique কি true করে দিলে যদি ডেটাবেজে আছে এমন কোন ভ্যালু পুনরায় দেয়ার চেষ্টা করা হয়, সেটা E11000 এরর দিবে। সেটা খানিকটা ambiguous হতে পারে। 
{% endhint %}

### ইনস্টল

```text
npm install --save mongoose-unique-validator
```

### স্কিমা এডিট 

{% code title="user.js" %}
```javascript
    username: 
        {
            type: String,
            unique: true
        }
        
    //...
    //...
    //...
    
    
    userSchema.plugin(uniqueValidator)
```
{% endcode %}





