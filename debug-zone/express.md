# Express \(এক্সপ্রেস\)

## এক্সপ্রেস 405 এর বদলে 200 OK দিচ্ছে।

রেসপন্সে json\(\) থাকতে পারবে না।

```javascript
res.status(405).send({"error" : "some error"});
```



















