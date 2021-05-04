# populate\(\) - পপুলেট

ধরি, user একটা কালেকশন, যেটা দেখতে নিচের মত,

<table>
  <thead>
    <tr>
      <th style="text-align:left">User</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Name</td>
    </tr>
    <tr>
      <td style="text-align:left">Password</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>blogs</p>
        <p>[ ]</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">id</td>
    </tr>
  </tbody>
</table>

যেখানে blogs ফিল্ডটা হচ্ছে একটা অ্যারে, যেটাতে থাকবে তার লেখা ব্লগগুলোর id। এই idগুলো রেফার করে blogs নামের আরেকটা কালেকশনে থাকা ব্লগগুলোকে, যে কালেকশনটা দেখতে নিচের মতন।

| Blog |
| :--- |
| title |
| author |
| url |
| id |

যদি user -এর ডেটাতে ব্লগের আইডির তালিকার বদলে সেগুলোর নাম দেখাতে চাইলে populate ব্যবহার করা যেতে পারে নিচের ধাপগুলোতে - 

* user মডেল মডিফাই করে blogs ফিল্ডটাকে blog মডেলের একটা রেফারেন্স বানানো - 

```javascript
    blogs: [ 
        {
        type: mongoose.Schema.Types.ObjectId,
        ref: 'blog'
        }
```

* blogs-এর যে রাউটে সেগুলোকে ডাটাবেজ থেকে ফেচ করা হবে, সেখানে populate\(\) ফাংশন যুক্ত করা -

```javascript
        const users = await User.find({}).populate('blogs', 'title');
```

এখানে দুটো জিনিস হচ্ছে - 

* বলে দেয়া হচ্ছে যে, blogs ফিল্ডটাকে populate করতে।
* বাই ডিফল্ট, সেটা populate করে সবগুলো \(title, url, user ফিল্ডই দেখাবে\)।
* তবে উপরের মত করে কোন ফিল্ড দেখাতে হবে, তা বলে দেয়া যেতে পারে। id ফিল্ড অবশ্যই দেখাবে।

