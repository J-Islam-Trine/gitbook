# যেভাবে Schema লিখতে হয়\(How to write a schema for a document\)

ধরি, আমরা blogPost নামে একটা ডকুমেন্টের জন্য Schema লিখবো, যেটাতে থাকবে title, date, body, images ফিল্ডগুলো।

প্রথমেই **Schemas** ফোল্ডারে গিয়ে blogPost.js নামে একটা ফাইল বানাই।

এরপর সেটাতে একটা object বানাবো, যেটাতে নিচের ভ্যালুগুলো দিবো।

```javascript
{
    name: 'blogPost',
    type: 'document',
    title: 'Blog Post',
    fields: [
    
    
    
    ]

}
```

**name -&gt;** এই ডকুমেন্টের নাম। name-এর ভ্যালুতে স্পেস থাকতে পারবে না।

**type** -&gt; অবশ্যই **document** হবে।

**title** -&gt; CMS-এ ডকুমেন্টটাকে যে নামে দেখাবে সেটা। '

fi**elds** -&gt; কী কী ফিল্ড থাকবে। এটা array হবে।



### ফিল্ডস

উপরের প্যারামিটার দিয়েই এবারে আমরা এই ডকুমেন্টের ফিল্ডগুলো লিখতে পারি। যেটার প্রতিটা ভ্যালু আবার একটা অব্জেক্ট হবে।

```javascript
{
    name: 'blogPost',
    type: 'document',
    title: 'Blog Post',
    fields: [
        {
            name: "title",
            type: "string",
            title: "Post Title"
        }
    
    
    ]

}
```

