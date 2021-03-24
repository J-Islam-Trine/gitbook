# টোকেন ভিত্তিক অথেনটিকেশন\(Token based authentication\)

* jsonwebtoken ইনস্টল করি।

```text
npm install --save jsonwebtoken
```

* jsonwebtoken ইমপোর্ট করে নিয়ে আসি।

{% code title="controller/loginController.js" %}
```javascript
const jwt = require('jsonwebtoken')
```
{% endcode %}

* টোকেনের জন্য ইউজার-এর ডিটেইল দিয়ে নতুন একটা অবজেক্ট ক্রিয়েট করি।

{% code title="controller/logincontroller.js" %}
```javascript
 const dataForToken = 
{
        username: userSubmittedusername,
        id: userSubmittedId
}
```
{% endcode %}

* .env ফাইলে SECRET নামে একটা ভ্যালু ক্রিয়েট করি। এটা যে কোন কিছু হতে পারে।

```javascript
SECRET = secretPassThatOnlyYouKnow
```

* এবারে টোকেন জেনারেট করা যাবে।

{% code title="controller/loginController.js" %}
```javascript
const token = jwt.sign(dataForToken, process.env.SECRET)
```
{% endcode %}

### রেফারেন্স

{% page-ref page="../../../debug-zone/undefined/user-login-controller.md" %}





