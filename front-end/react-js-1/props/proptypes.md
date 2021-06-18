# প্রপ চেক করা\(proptypes\)

## PropTypes কী?

একটা লাইব্রেরি যা দিয়ে কোন কম্পোনেন্টে সঠিক প্রপস পাচ্ছে কি না তা যাচাই করা যায়।

### ইনস্টলেশন

```javascript
npm install --save prop-types
```

### যেভাবে ব্যবহার করতে হবে

যে কম্পোনেন্টের জন্য প্রপ চেক করতে হবে , সেটার নিচে গিয়ে যুক্ত করতে হবে।

```javascript
import PropTypes from 'prop-types'
const Message = ({type, content, handler}) => {
    //...
    //...
    
    return(
    //...
    //...
    )
}

Message.propTypes = {
        type: PropTypes.string.isRequired,
        content: PropTypes.string,
        handler: Proptypes.func.isRequired
        }
```





