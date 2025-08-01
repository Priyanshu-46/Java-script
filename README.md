# Java-script
// for of

// ["", "", ""]
// [{}, {}, {}]
arrays can store objects (and mixed types too). Objects are stored by reference, so the array holds pointers to those objects.
# for (const num of arr)

const arr = [1, 2, 3, 4, 5]

for (const num of arr) {
    console.log(num);
}
for...of is used to iterate over the values of an iterable (like arrays, strings, Maps, Sets).

On each iteration, num takes the value of the current array element:

1 → 2 → 3 → 4 → 5

const greetings = "Hello world!"
for (const greet of greetings) {
    //console.log(`Each char is ${greet}`)
}

// Maps
a Map is a built-in collection that holds key-value pairs and is more powerful/flexible than plain objects for certain use cases.A Map in JavaScript is a collection of key-value pairs where each key is unique and the insertion order is preserved.
 It allows any value (both objects and primitive values) to be used as either a key or a value.

const map = new Map()
map.set('IN', "India")
map.set('USA', "United States of America")
map.set('Fr', "France")
map.set('IN', "India")


// console.log(map);

for (const [key, value] of map) {
    // console.log(key, ':-', value);
}

const myObject = {
    game1: 'NFS',
    game2: 'Spiderman'
}

// for (const [key, value] of myObject) {
//     console.log(key, ':-', value);
    
// }
❌ will throw an error if myObject is a plain JavaScript object because plain objects are not iterable with for...of.

🔹 Why?
for...of works on iterables: arrays, strings, Maps, Sets, etc.

A plain object ({}) is not iterable by default.

# for in loop
🔹 Key Points
-Iterates keys (property names), not values.
-To get the value, use object[key].
-Includes inherited enumerable properties from the prototype chain.

const myObject = {
    js: 'javascript',
    cpp: 'C++',
    rb: "ruby",
    swift: "swift by apple"
}

for (const key in myObject) {
    console.log(`${key} shortcut is for ${myObject[key]}`);
}

const programming = ["js", "rb", "py", "java", "cpp"]

for (const key in programming) {
    console.log(programming[key]);
}

 const map = new Map()
 map.set('IN', "India")
 map.set('USA', "United States of America")
 map.set('Fr', "France")
 map.set('IN', "India")
 for (const key in map) {
    console.log(key);
}

# forEach 
the forEach() method is a built-in array method used to iterate over array elements and execute a function for each element.

It’s different from for, for...in, and for...of because it’s a method, not a loop keyword.
🔹 Key Points about forEach()
Only works on arrays (not on objects directly).

Always iterates in order (from index 0 to last).

Cannot break/return early — if you need to exit early, use for or for...of.

It modifies the array if you change the element via reference (for objects or arrays inside it).

const coding = ["js", "ruby", "java", "python", "cpp"]

coding.forEach( function (val){
     console.log(val);
 } )

 coding.forEach( (item) => {
    console.log(item);
 } )

 function printMe(item){
     console.log(item);
 }

 coding.forEach(printMe)

coding.forEach( (item, index, arr)=> {
     console.log(item, index, arr);
 } )

const myCoding = [
    {
        languageName: "javascript",
        languageFileName: "js"
    },
    {
        languageName: "java",
        languageFileName: "java"
    },
    {
        languageName: "python",
        languageFileName: "py"
    },
]

myCoding.forEach( (item) => {
    
    console.log(item.languageName);
} )
