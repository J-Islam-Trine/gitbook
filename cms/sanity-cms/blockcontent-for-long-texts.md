# লম্বা লেখার জন্য ব্লক কন্টেন্ট \(BlockContent for long texts\)

### কেন ব্লক কন্টেন্ট?

ব্লক কন্টেন্ট যুক্ত করলে ইউজার - 

* কন্টেন্ট ফরম্যাট করতে পারে।
* কোড ব্লক বা ইমেজ যুক্ত করতে পারে, সেটিও আবার লেখার মধ্যে।

### কীভাবে ব্লক কন্টেন্ট স্কিমাতে যুক্ত করা যাবে?

ধরি, আমার একটা স্কিমা লেখা আছে\([**এখান**](schema-how-to-write-a-schema-for-a-document.md) থেকে blogPost স্কিমাটার কথাটাই ধরা যাক\)।

প্রথমে fields-এর ভেতর একটা array টাইপের কন্টেন্ট যুক্ত করবো।

```javascript
{
            name: 'shortIntro',
            type: 'array',
            title: 'Short Introduction',
}
```

এবারে সেটার মধ্যে **of** নামে আরেকটা array ভ্যালু দিবো, যেখানে আমি ব্লক কন্টেন্টে কী কী রাখতে চাই তা লিখে দিবো। 

```javascript
        {
            name: 'shortIntro',
            type: 'array',
            title: 'Short Introduction',
            of: [
                {
                    type: 'block'
                }
            ]
        }
```

