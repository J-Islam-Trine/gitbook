# পেজ \(pages\)

### Page কী?

NextJS-এ Page হচ্ছে একটি রিঅ্যাক্ট কম্পোনেন্ট। প্রতিটা পেজের রাউট সেই পেজের নামের উপর নির্ভর করে।

যেমন, 

pages/new-post.js এর রাউট হবে '/new-post.js'

আবার 

pages/posts/new-post.js-এর রাউট হবে '/posts/new-post.js'



### Page-এর বেসিক ফর্ম

{% code title="contact.jsx" %}
```javascript
function Contact()
{
    return (
        <div>
            <h1>Contact</h1>
        </div>
    )
}

export default Contact
```
{% endcode %}







