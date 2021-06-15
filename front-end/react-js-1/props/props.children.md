# চাইল্ড কম্পোনেন্ট \(props.children\)

### props.children কী?

সব কম্পোনেন্টেরই একটা বিশেষ prop থাকেই, সেটা হচ্ছে children প্রপ।  এটা দিয়ে children এলিমেন্টগুলা ডিরেক্ট পাস করা যায়।



### কীভাবে?

নিচে Content কম্পোনেন্টটাকে Layout দিয়ে র‍্যাপ করা হচ্ছে।

```text
<Layout>
<Content />
<Layout/>
```

এর মানে হচ্ছে এটার চাইল্ড আছে একটা , Content. 

**এমনিতে আমরা কম্পোনেন্ট নিচের মত লেখি যখন সেটার কোন চাইল্ড থাকে না।**

```text
<Content />
```

এখন Layout কম্পোনেন্ট child-গুলোকে নিচের মত করে ব্যবহার করতে পারবে।

```text
const Layout = (props) => {
return (
    <h2>Header</h2>
    {props.children}
    <h2>footer</h2>
)

}
```

### নোট

{% hint style="info" %}
**যখন কম্পোনেন্টগুলো র‍্যাপ করা হয়  না, তখনও তার props-এর মধ্যে children থাকে, তবে সেটা হয় একটা খালি অ্যারে।**
{% endhint %}

### একাধিক কম্পোনেন্টের ক্ষেত্রে

কখনো কখনো একাধিক কম্পোনেন্ট পাঠাতে হতে পারে। তখন সাধারণ সময়ের মত props হিসেবেই তা পাস করা যাবে।

```text
import Blog from './component/blog.jsx'
import Content from './component/content.jsx'

<Layout blog={Blog} content={Content}></Layout>
```

```text
const Layout = (props) => {
return (
    <h2>Header</h2>
    <div>
    {props.content}
    </div>
    {props.blog}
    <h2>footer</h2>
)

}
```

