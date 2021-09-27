# Cypress-এর বিভিন্ন কমান্ড\(Different commands of Cypress\)

### কোন পৃষ্ঠাতে যেতে - cy.visit

এটা দিয়ে যে কোন লিংকে যাওয়া যায়।

```javascript
cy.visit('http://localhost:3000/')
```

### লেখা খুঁজতে - cy.contains

এটা দিয়ে পেইজের যে কোন স্থানে থাকা যে কোন লেখা সার্চ করা যায়, এমনকি বাটন টেক্সট পর্যন্তও। 

```javascript
cy.contains('some text')
```

এই পর্যন্তই ছেড়ে দিলে এটাই টেস্ট হিসাবে কাজ করবে।



