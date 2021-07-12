![](codewars.png)

# Краснов Андрей

____
# Задание 1 - Unique In Order
Implement the function unique_in_order which takes as argument a sequence and returns a list of items without any elements with the same value next to each other and preserving the original order of elements.

For example:

uniqueInOrder('AAAABBBCCDAABBB') == ['A', 'B', 'C', 'D', 'A', 'B']
uniqueInOrder('ABBCcAD')         == ['A', 'B', 'C', 'c', 'A', 'D']
uniqueInOrder([1,2,2,3,3])       == [1,2,3]
# Выполнение:
```html
var uniqueInOrder=function(iterable){
  var tmp = [];
  for(var i = 0 ; i<iterable.length ; i++){
    if(iterable[i] !=iterable[i+1]){
      tmp.push(iterable[i])
    }
  }
  return tmp;
}
```
____
# Задание 2 - Is this a triangle?
Implement a method that accepts 3 integer values a, b, c. The method should return true if a triangle can be built with the sides of given length and false in any other case.

(In this case, all triangles must have surface greater than 0 to be accepted).
# Выполнение:
```html
function isTriangle(a,b,c)
{
   if (a+b > c && a+c > b && c+b > a)
          return true;
        else
          return false;

}
```
____
# Задание 3 - Don't give me five!
In this kata you get the start number and the end number of a region and should return the count of all numbers except numbers with a 5 in it. The start and the end number are both inclusive!

Examples:

1,9 -> 1,2,3,4,6,7,8,9 -> Result 8
4,17 -> 4,6,7,8,9,10,11,12,13,14,16,17 -> Result 12
The result may contain fives. ;-)
The start number will always be smaller than the end number. Both numbers can be also negative!
# Выполнение:
```html
function dontGiveMeFive(start, end)
{
  var res=0;
   
  for(var i=start;i<end+1;i++)
    {
    var  str=i.toString();  
    if(str.search('5')==-1)
        {
        res++;
        }
      }
  return res;
}
```
____
# Задание 4 - Exes and Ohs
Check to see if a string has the same amount of 'x's and 'o's. The method must return a boolean and be case insensitive. The string can contain any char.

Examples input/output:

XO("ooxx") => true
XO("xooxx") => false
XO("ooxXm") => true
XO("zpzpzpp") => true // when no 'x' and 'o' is present should return true
XO("zzoo") => false
# Выполнение:
```html
function XO(str) {
  str=str.toLowerCase();
  var x=0;
  var o=0;
  for(var i=0;i<str.length;i++)
  {   if(str[i]=='x')
     { x++;}
    if(str[i]=='o')
     { o++;}
  }
   if(x==o)
     return true;
  else
    return false;

}
```
____
# Задание 5 - Write Number in Expanded Form
You will be given a number and you will need to return it as a string in Expanded Form. For example:

expandedForm(12); // Should return '10 + 2'
expandedForm(42); // Should return '40 + 2'
expandedForm(70304); // Should return '70000 + 300 + 4'
NOTE: All numbers will be whole numbers greater than 0.

If you liked this kata, check out part 2!!
# Выполнение:
```html
function expandedForm(num) {
 var str=num.toString();
 var len=str.length-1;
 var check=0;
 var rez='';
 
  for(var i=0;i<str.length;i++)
    {
      if(str[i]!=0) { 
        if (check!=0)
          {rez=rez+' + '}
      var j=Number(str[i])*Math.pow(10,len);
      rez=rez+j.toString();
        check++;
      }
      len--;
    }
    
 return rez;   
}
```
____
# Задание 6 - The Supermarket Queue
There is a queue for the self-checkout tills at the supermarket. Your task is write a function to calculate the total time required for all the customers to check out!

input
customers: an array of positive integers representing the queue. Each integer represents a customer, and its value is the amount of time they require to check out.
n: a positive integer, the number of checkout tills.
output
The function should return an integer, the total time required.

Important
Please look at the examples and clarifications below, to ensure you understand the task correctly :)

Examples
queueTime([5,3,4], 1)
// should return 12
// because when there is 1 till, the total time is just the sum of the times

queueTime([10,2,3,3], 2)
// should return 10
// because here n=2 and the 2nd, 3rd, and 4th people in the 
// queue finish before the 1st person has finished.

queueTime([2,3,10], 2)
// should return 12
# Выполнение:
```html
function queueTime(customers, n) {
 var arr = new Array(n).fill(0);

  for (var i = 0; i < customers.length; i++) {
    var idx = arr.indexOf(Math.min(...arr));
    arr[idx] += customers[i];
  }

  return Math.max(...arr);

}
```
____
# Задание 7 - Mexican Wave
In this simple Kata your task is to create a function that turns a string into a Mexican Wave. You will be passed a string and you must return that string in an array where an uppercase letter is a person standing up. 
Rules
 1.  The input string will always be lower case but maybe empty.

 2.  If the character in the string is whitespace then pass over it as if it was an empty seat
Example
wave("hello") => ["Hello", "hEllo", "heLlo", "helLo", "hellO"]
# Выполнение:
```html
function positiveSum(arr) {
  var result = 0;
for (let i = 0; i < arr.length; i++) {
    if (arr[i] > 0) {
        result += arr[i];
    }
}
  return result;
}
```
____
# Задание 8 - Roman Numerals Decoder
Create a function that takes a Roman numeral as its argument and returns its value as a numeric decimal integer. You don't need to validate the form of the Roman numeral.

Modern Roman numerals are written by expressing each decimal digit of the number to be encoded separately, starting with the leftmost digit and skipping any 0s. So 1990 is rendered "MCMXC" (1000 = M, 900 = CM, 90 = XC) and 2008 is rendered "MMVIII" (2000 = MM, 8 = VIII). The Roman numeral for 1666, "MDCLXVI", uses each letter in descending order.

Example:

solution('XXI'); // should return 21
# Выполнение:
```html
function value(r) {
        if (r == 'I')
            return 1;
        if (r == 'V')
            return 5;
        if (r == 'X')
            return 10;
        if (r == 'L')
            return 50;
        if (r == 'C')
            return 100;
        if (r == 'D')
            return 500;
        if (r == 'M')
            return 1000;
        return -1;
    }

function solution(str){
  var res = 0;
 
        for (i = 0; i < str.length; i++) {
            
            var s1 = value(str.charAt(i));

            if (i + 1 < str.length) {
                var s2 = value(str.charAt(i + 1));
 
                
                if (s1 >= s2) {
                    res = res + s1;
                } else {
                    res = res + s2 - s1;
                    i++;
                }
            } else {
                res = res + s1;
            }
        }
 
        return res; 
}
```
____
# Задание 9 - Moving Zeros To The End
Write an algorithm that takes an array and moves all of the zeros to the end, preserving the order of the other elements.

moveZeros([false,1,0,1,2,0,1,3,"a"]) // returns[false,1,1,2,1,3,"a",0,0]
# Выполнение:
```html
var moveZeros = function (nums) {
  
let count = 0;
        for (let i = 0; i < nums.length; i++){
            if(nums[i] !== 0){
                nums[count++] = nums[i];
            }
        }

        for (let i = count; i < nums.length; i++){
            nums[i] = 0;
        }
        return nums;   
 
}
```
____
# Задание 10 - First non-repeating character
Write a function named first_non_repeating_letter that takes a string input, and returns the first character that is not repeated anywhere in the string.

For example, if given the input 'stress', the function should return 't', since the letter t only occurs once in the string, and occurs first in the string.

As an added challenge, upper- and lowercase letters are considered the same character, but the function should return the correct case for the initial letter. For example, the input 'sTreSS' should return 'T'.

If a string contains all repeating characters, it should return an empty string ("") or None -- see sample tests.
# Выполнение:
```html
function firstNonRepeatingLetter(str) {
  console.log(str);
  var string=str.toLowerCase()
  for (var i = 0; i < string.length; i++) {
    var c = string.charAt(i);
    if (string.indexOf(c) == i && string.indexOf(c, i + 1) == -1) {
      return str.charAt(i);
    }
  }
  return '';
}
```
