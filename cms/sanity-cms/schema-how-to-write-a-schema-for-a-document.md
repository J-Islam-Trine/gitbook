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

{% code title="schema/blogPost.js" %}
```javascript
const blogPost = {
    name: 'blogPost',
    type: 'document',
    title: 'Blog Post',
    fields: [
        
        
        {
            name: "title",
            type: "string",
            title: "Post Title"
        },
        
        
        {
            name: 'postBody',
            type: 'array',
            title: 'Post Content',
            of: [
                {
                    type: 'block'
                }
            ]
        },
        
        
        {
            name: 'publishDate',
            type: 'date',
            title: 'Publish Date'
        },
        
        
        {
            title: 'Your Photo',
            name: 'profilePhoto',
            type: 'image'

        }
    ]

}

export default blogPost
```
{% endcode %}

উপরের fields-এর দ্বিতীয় ভ্যালুটা হলো ব্লক কন্টেন্ট, সেটার নোটটা আছে [**এখানে**](blockcontent-for-long-texts.md)। এরপরেরটা তারিখের জন্য আর তারপরেরটা হচ্ছে image-এর জন্য।

### Schema ফাইলে blogPost স্কিমা যুক্ত করা

এবারে আমাদেরকে schemas ফোল্ডারের মধ্যে থাকা schema ফাইলে সেটাকে ইমপোর্ট করে আনতে হবে আর যুক্ত করতে হবে।

{% code title="schema/schema.js" %}
```javascript
import blogPost from './blogPost.js'

// Then we give our schema to the builder and provide the result to Sanity
export default createSchema({
    name: 'pages',
    types: schemaTypes.concat([
      pageContent,
      blogPost
    ])
})

```
{% endcode %}

