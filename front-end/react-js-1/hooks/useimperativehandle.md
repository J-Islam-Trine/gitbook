# ইম্পারেটিভ হ্যান্ডল হুক \(useImperativeHandle\)

## useImperativeHandle কী?

এটা একটা হুক যা কোন চাইল্ড কম্পোনেন্টের কাছে তার প্যারেন্ট থেকে আসা \(App-&gt;Home\) ref-এর ভ্যালু ম্যানিপুলেট করতে দেয়। যা আরো বেশি কন্ট্রোল এনে দেয় refএর উপর।

{% hint style="info" %}
**useImperativeHandle সব সময় React.forwardRef\(\)-এর সঙ্গে ব্যবহার করা উচিত।**
{% endhint %}

## ইউজ কেস

চাইল্ড কম্পোনেন্টের মেথড বা ভ্যালু প্যারেন্টের কাছে এক্সপোজ করার জন্য।

## কীভাবে

```javascript
const Greeting = React.forwardRef((props, ref) => {
    //...
    function hello()
    {
    console.log(`hello!`)
    }
    
    useImperativeHandle(ref, function(){
        return {
            hello
        }
    })

})
```

