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

// const coding = ["js", "ruby", "java", "python", "cpp"]


// const values = coding.forEach( (item) => {
//     //console.log(item);
//     return item
// } )

// console.log(values);

const myNums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

// const newNums = myNums.filter( (num) => {
//     return num > 4
// } )

// const newNums = []

// myNums.forEach( (num) => {
//     if (num > 4) {
//         newNums.push(num)
//     }
// } )

// console.log(newNums);

#filter function 
In JavaScript, filter() is an array method that creates a new array containing all elements that pass a test (condition) provided by a function.

It does not modify the original array.

✅ Syntax
array.filter(function(element, index, array) {
    // return true to keep element
});
Parameters:

element → current item in the array
index → current position (optional)
array → the array being processed (optional)

const books = [
    { title: 'Book One', genre: 'Fiction', publish: 1981, edition: 2004 },
    { title: 'Book Two', genre: 'Non-Fiction', publish: 1992, edition: 2008 },
    { title: 'Book Three', genre: 'History', publish: 1999, edition: 2007 },
    { title: 'Book Four', genre: 'Non-Fiction', publish: 1989, edition: 2010 },
    { title: 'Book Five', genre: 'Science', publish: 2009, edition: 2014 },
    { title: 'Book Six', genre: 'Fiction', publish: 1987, edition: 2010 },
    { title: 'Book Seven', genre: 'History', publish: 1986, edition: 1996 },
    { title: 'Book Eight', genre: 'Science', publish: 2011, edition: 2016 },
    { title: 'Book Nine', genre: 'Non-Fiction', publish: 1981, edition: 1989 },
  ];

  let userBooks = books.filter( (bk) => bk.genre === 'History')

  userBooks = books.filter( (bk) => { 
    return bk.publish >= 1995 && bk.genre === "History"
})
  console.log(userBooks);

myCoding.forEach( (item) => {
    
    console.log(item.languageName);
} )

const myNumers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

// const newNums = myNumers.map( (num) => { return num + 10})

const newNums = myNumers
                .map((num) => num * 10 )
                .map( (num) => num + 1)
                .filter( (num) => num >= 40)

console.log(newNums);

#Reduce() ................

 The reduce() method in JavaScript is a powerful array method that reduces the array to a single value by applying a function cumulatively to its elements.

const myNums = [1, 2, 3]
 const myTotal = myNums.reduce(function (acc, currval) {
    console.log(`acc: ${acc} and currval: ${currval}`);
return acc + currval
 }, 0)

const myTotal = myNums.reduce( (acc, curr) => acc+curr, 0)

console.log(myTotal);


const shoppingCart = [
    {
        itemName: "js course",
        price: 2999
    },
    {
        itemName: "py course",
        price: 999
    },
    {
        itemName: "mobile dev course",
        price: 5999
    },
    {
        itemName: "data science course",
        price: 12999
    },
]

const priceToPay = shoppingCart.reduce((acc, item) => acc + item.price, 0)

console.log(priceToPay);
