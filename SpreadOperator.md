```
function sum(a, b) {
  return a + b;
}
const res = sum(1, 4);
console.log(res) //5

const res1 = sum(1, 4, 3, 2);
console.log(res1) //


function sum1(){
  console.log(arguments.length); //2
  console.log(arguments[0]); //1
  
  console.log(arguments[0] + arguments[1]); //3
}

sum1(1,2);


function sum2(...args){
  let sum = 0;
  for(let arg of args){
    sum =  sum + arg;
  }
  
  return sum;
}

console.log(sum2(1)); //1
console.log(sum2(1,2,3)); //6

console.log(Math.max(1,2)); //2
console.log(Math.max(1,2,3,4,99)); //99


let arr = [1,"alex","alex@test.com","HYD"];
let[id,name, ...remainingdata] = arr;
console.log(name); //alex
console.log(remainingdata); //[ 'alex@test.com', 'HYD' ]


let userDetails1 = {name: "Alex", age: 21};
let userDetails2 = {email: "alex@test.com"}
let userDetails = {...userDetails1, ...userDetails2};
console.log(userDetails); //{ name: 'Alex', age: 21, email: 'alex@test.com' }



//Arracopy
arr1 = [1,2];
arr2 = arr1; //[1,2]
arr1[0] = 10;
console.log(arr2); [10,2]

a = 10;
b = a; //10
a = 100;
console.log(b); //10

_arr1 = [1,2];
_arr2 = [..._arr1] 
_arr1[0] = 10;
console.log(_arr2); [1,2]


let arr3 = [0, 1, 2];
let arr4 = [3, 4, 5];

//  Append all items from arr2 onto arr1
arr5 = [...arr3, ...arr4];
console.log(arr5); //[ 0, 1, 2, 3, 4, 5 ]


let userDetails4 = {name: "Alex", age: 21, email : "alex@test.com"};
userDetails4.address = "Hyd";
userDetails4.age = 22;
console.log(userDetails4);
```




