# লিংক \(Link\)

### next/link

এমনিতে a ট্যাগ দিয়ে এক রাউটে অন্য রাউট\(পেজ\) লিংক করলে সেখানে রিলোড হয়ে যাবে, কিন্তু সেই a ট্যাগটা দিয়েই যদি link ক্রিয়েট করে দেয়া হয়, তাহলে সেটা অনেকটা SPAএর মত লোড হবে রিলোড ছাড়াই।

### প্রথমে, 

next/link ইমপোর্ট করতে হবে।

```javascript
import Link from 'next/link'
```

### তারপর,

ধরি আমার লিংকটি হচ্ছে 

```javascript
<a href="/posts/first-post">First Post</a>
```

এটা Link ইউজ করে লিখলে হবে - 

```javascript
<Link href="/posts/first-post"> 
<a>First Post</a>
</Link>
```

{% hint style="info" %}
production বিল্ডে Next.js Link-গুলোকে ব্যাকগ্রাউন্ডে প্রিফেচ করে। যার ফলে তাতে ক্লিক করলে সেটা প্রায় সঙ্গে সঙ্গে রিলোড হয়ে যায়।
{% endhint %}



