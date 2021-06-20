# ইভেন্ট টেস্টিং \(testing events\)

ইভেন্ট টেস্টিং-এর জন্য ইভেন্ট হ্যান্ডলারটা কম্পোনেন্টে বাইরে থেকে পাস করতে হবে। 

{% tabs %}
{% tab title="App.js" %}
```javascript
import Quest from './components/mini/singleQuest'

const App = () => {
    //...
    //...
    
    
    const handleDeletion = (title) => {
  console.log(title)
}

return(
    <div>
        //...
    //...
    <Quest quest={que} handleDeletion={handleDeletion}/>
    </div>

)

}
```
{% endtab %}

{% tab title="singleQuest.jsx" %}
```javascript
const Quest = ({quest, handleDeletion}) => {


    return(
        <div className='quests'>
             <h2 className='title'>{quest.title}</h2>
             <p>{quest.detail}&nbsp; &nbsp;
             <button className='delButton' 
             onClick={handleDeletion(quest.title)}>
             Delete
             </button>
             </p>
        </div>
    )
}

export default Quest
```
{% endtab %}

{% tab title="singleQuest.test.js" %}
```javascript
import React from 'react'
import '@testing-library/jest-dom/extend-expect'
import { render, fireEvent } from '@testing-library/react'
import Quest from './singleQuest'

test('renders content', ()=> {
    const newQuest = {
        title: "Dampened Spirits",
detail: "Put Maven Black-Briar\'s 
        competition out of business."
    }
    const mockHandler = jest.fn()

    const component = render(
            <Quest quest={newQuest} 
            handleDeletion={mockHandler}/>)

    const delButton = component.
                        container.
                        querySelector('.delButton')
    fireEvent.click(delButton)
    expect(mockHandler.mock.calls).toHaveLength(1)

})
```
{% endtab %}
{% endtabs %}

### কীভাবে এটা কাজ করে?

এখানে একটা মক হ্যান্ডলার ক্রিয়েট করা হচ্ছে যেটা ফায়ার হওয়া ইভেন্টগুলা **mock.calls**-এ সেভ করে রাখে। তারপর বাটনটাকে সিলেক্ট করে, সেটার জন্য fireEvent দিয়ে ক্লিক ইভেন্ট রান করা হচ্ছে। তারপর mockHanlder-এর mock.calls-এ কয়টা ভ্যালু আছে তা দেখা হচ্ছে, যদি তা ১ হয় তার মানে হচ্ছে আমাদের ইভেন্টটা ঠিক ভাবেই ফায়ার হচ্ছে। 

