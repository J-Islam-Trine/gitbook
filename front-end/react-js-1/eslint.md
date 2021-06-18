# লিন্টিং \(ESLint\)

## লিন্টিং কী?

লিন্টিং মানে হচ্ছে নির্দিষ্ট কিছু নিয়মের ভিত্তিতে অ্যাপের প্রোগ্রাম করার সময়ের বা স্টাইলে হওয়া ভুল বের করা।

## ESLint

CRA-তে ESLint স্বয়ংক্রিয় ভাবে যুক্ত করা থাকে। 

## ESLint কনফিগারেশন \(Configuration\)

```javascript
/* eslint-env node */
module.exports = {
  "env": {
      "browser": true,
      "es6": true,
      "jest/globals": true 
  },
  "extends": [ 
      "eslint:recommended",
      "plugin:react/recommended"
  ],
  "parserOptions": {
      "ecmaFeatures": {
          "jsx": true
      },
      "ecmaVersion": 2018,
      "sourceType": "module"
  },
  "plugins": [
      "react", "jest"
  ],
  "rules": {
      "indent": [
          "error",
          2  
      ],
      "linebreak-style": [
          "error",
          "windows"
      ],
      "quotes": [
          "error",
          "single"
      ],
      "semi": [
          "error",
          "never"
      ],
      "eqeqeq": "error",
      "no-trailing-spaces": "error",
      "object-curly-spacing": [
          "error", "always"
      ],
      "arrow-spacing": [
          "error", { "before": true, "after": true }
      ],
      "no-console": 0,
      "react/prop-types": 0
  },
  "settings": {
    "react": {
      "version": "detect"
    }
  }
}
```

## রান করার জন্য

```javascript
eslint .
```



