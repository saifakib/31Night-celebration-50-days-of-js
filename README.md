# 31Night Celebration With JS Challange
## Doing Thirty first (31) night celebration solving [codedamn 50 days of js](https://codedamn.com/50-days-of-js) problems

#### Day1: Returns a random number
- Create a function which returns a random number in the given range of values both inclusive
```
function randomNumberGeneratorInRange(rangeStart, rangeEnd) {
	return Math.random() * (rangeEnd - rangeStart) + rangeStart
}
console.log(`My random number: ${randomNumberGeneratorInRange(5, 100)}`)
```

#### Day2: Reverse a string
- String can be reversed by iterating it and storing it in reverse order
- String can also be reversed by converting it to array, then joining it after reversing
```
const str = "JavaScript is awesome"
function reverseAString(str) {
    return str.split('').reverse().join('')
}
console.log(`Reversed string is: ${reverseAString(str)}`)
```

#### Day3: Reverse a given integer number
- The remainder of the number can be fetched and the number can be divided by 10 to remove the the digit in loop till number becomes
- A simple approach to reverse a number could also be to convert it in to a string and then reverse it
```
const num = 3849;
function reverseGivenInteger(num) {
    let reverseNum = parseFloat(num.toString().split('').reverse().join('')) * Math.sign(num)
    return reverseNum
}
console.log(`Reversed integer is: ${reverseGivenInteger(num)}`)
```

#### Day4: Convert the time input given in 12 hours format to 24 hours format
- The check for 'AM' and 'PM' can be verified using endsWith String method
- An extra 0 would be needed if the hours have single digit
```
const time = '12:10AM';
function convertTo24HrsFormat(time) {
    const isPM = time.includes('PM') ? true : false
    let timeWithoutModifier = time.replace(/AM/gi,'').replace(/PM/gi,'')
    let [hours, minutes] = timeWithoutModifier.split(":");
    if(hours == '12') {
        hours = '00'
    }
    if(isPM) {
        hours = parseInt(hours, 10) + 12
    }
    return `${hours}:${minutes}`
}
console.log(`Converted time: ${convertTo24HrsFormat(time)}`)
```

#### Day5: Accepts a string argument and returns the count of characters between the first and last character 'X'
- indexOf and lastIndexOf are the methods on String which returns the position of the given string in the input string from start and end respectively
- If the match is not found, these methods return -1
```
const str = 'XeroX';
function getTheGapX(str) {
    
    const fIndex = str.indexOf('X')
    const lIndex = str.lastIndexOf('X')
    if('X' !== str[0]) { return -1 }
    if('X' !== str[str.length-1]) { return 0}

    const gapBeetweenX =  lIndex - fIndex
    return gapBeetweenX
}
console.log(`Gap between the X's: ${getTheGapX(str)}`)
```

#### Day6: Truncate a string to a certain number of words
```
const str = 'JavaScript is simple but not easy to master';
const wordLimit = 3
function truncateWithWordLimit(str, wordLimit) {

    return str.split(' ').slice(0,wordLimit).join(' ')
}
console.log(`Truncated string: ${truncateWithWordLimit(str, wordLimit)}`)
```

#### Day7: Create a regular expression to validate if the given input is valid Indian mobile number or not
- Regular expression check has to have an optional +91 or 0 in the beginning, then an optional space and 10 digits
- `test` method of regular expression can be used to validate if the mobile number pattern matches or not
```
const number = '+919876543210';
function validateMobile(number) {
    const regEx = /^(\+91|0)?( )?(\d{10})$/
    return regEx.test(number)
}
console.log(`is a valid Indian mobile number: ${validateMobile(number)}`)
```

#### Day8: Accepts two valid dates and returns the difference between them as number of days
- The difference between 2 dates in JavaScript will give the time difference in milliseconds
- Time difference can be converted in to days by dividing the 24Hrs time in milliseconds
```
const DAY_IN_MILLISECONDS = 1000 * 60 * 60 * 24;
function getDaysBetweenDates(dateText1, dateText2) {
    const firstDate = new Date(dateText1);
    const secondDate = new Date(dateText2);
    return (secondDate - firstDate) / DAY_IN_MILLISECONDS
    
}
console.log(`Days difference: ${getDaysBetweenDates('10/15/2020', '12/1/2020')}`)
```

#### Day9: Check if an object is empty or not in javaScript?
```
const obj = { key: 1 };
function isEmpty(obj) {
    return Object.keys(obj).length === 0
}
console.log(`is empty object: ${isEmpty(obj)}`)
```

#### Day10: Remove array element based on object property?
```
const array = [
    { field: "id", operator: "eq" },
    { field: "cStatus", operator: "eq" },
    { field: "money", operator: "eq" },
];
const filterField = "money"
function removeArrayElement(filterField) {
    return array.filter(item => item.field !== filterField)
}
console.log(`filtered array: ${removeArrayElement(filterField)}`)
```

#### Day11: Return the N-th value of the Fibonacci sequence
```
function fibo(n){
    if(n<=1) return 0
    if(n===2) return 1
    else return fibo(n-1) + fibo(n-2)
}
function fibonacci(n) {
	return fibo(n+1)
}
console.log(`fibonacci value at position 5: ${fibonacci(5)}`)
```

#### Day12: Given a number from 0 to 999,999,999,999, spell out that number in English.







