# ইমেজ \(Image\)

### next/image

img ট্যাগ দিয়ে ইমেজ অ্যাড করার বদলে next/image ব্যবহার করলে নিচের সুবিধাগুলো পাওয়া যায়-

* ইমেজগুলো ইউজারের রিকুয়েস্ট অনুসারে অপটিমাইজড হয়, যার ফলে অনেক বেশি ইমেজ থাকলেও বিল্ড টাইম বাড়ে না।
* বাই ডিফল্ট লেজি লোডিং হয়, যার মানে হচ্ছে, ভিউপোর্টের বাইরে থাকা ইমেজ লোড হয় না। 

### Image

next/image ইমপোর্ট করি।

```javascript
import Image from 'next/image'
```

তারপর &lt;img /&gt; এর বদলে সেটা ব্যবহার করি।

```javascript
 <Image src="/images/profile_pic.jpg"
            height={160}
            width={128}
            alt="profile picture"
            />
```







