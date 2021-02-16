# মঙ্গোডিবি থেকে ক্রিয়েট, রিড, আপডেট, ডিলিট \(MongoDB CRUD\)

**এখানে Person একটি মডেল।**

### সব এন্ট্রি

```javascript
const allPersons = await Person.find({})
res.json(allPersons)
```

### একটা এন্ট্রি

এটা কাজ করবে আইডির উপর ভিত্তি করে।

```javascript
const id = req.params.id;
const singlePerson = await Person.findById(id);
res.json(singlePerson);
```

### ডাটা পোস্ট করা

```javascript
const newData = new Person({
    name: 'some name',
    age: 41
})

const response = await newData.save();
res.json(response);
```

### ডাটা আপডেট করা

```javascript
const id = req.params.id;
const newData = {
    name: 'some name',
    age: 42
}

const response = await Person.findByIdAndUpdate(id, newData, {new: true});
res.json(response);
```

* newData কিন্তু model-এর অবজেক্ট নয় বরং প্লেইন অবজেক্ট।
* new: true মানে আপডেট করার পর নতুন ভ্যালু পাঠাবে। false দেয়া থাকলে পুরনোটা পাঠাতো।

### ডেটা ডিলিট করা

```javascript
    await Order.findByIdAndRemove(req.params.id);
    res.status(204).end();
```

* এই ক্ষেত্রে রেসপন্সে কোন ডেটা আসবে না।
* ডিলিট হোক আর না হোক, স্ট্যাটাস কোড 204 ই দেখাবে।

