# ফর্ম হ্যান্ডল করা \(Handling Form\)

রিঅ্যাক্টে ফর্মের জন্য সেটার হ্যান্ডলার ফাংশনটা্র নামটা শুধু পাস করে দিতে হবে।

```javascript
const SomeComponent = () => 
{
function formHandler(e)
{
e.preventDefault()
//.......
//.......
//.......
}

return(
//...
<form onSubmit={formHandler}>
//...
//...
</form>


)



}
```





