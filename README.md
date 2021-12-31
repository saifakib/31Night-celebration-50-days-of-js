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








