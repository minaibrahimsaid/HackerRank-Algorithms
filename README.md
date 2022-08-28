# HackerRank Algorithms

This repo is to document **[Hackerrank](https://www.hackerrank.com/dashboard)** solutions with steps and a few tips. using JS <3

## :bookmark_tabs: Menu

- [Problems](#scroll-problems)
  - [Funny String](#funny-string)
  - [Alternating Characters](#alternating-characters)
  - [String Construction](#string-construction)
  - [Two Strings](#two-strings)
  - [Game of Thrones - I](#game-of-thrones)
  - [Strange Counter](#strange-counter)
- [Tips](#Tips)

## :scroll: Problems

<details>
 <summary id="funny-string"><b><u><font size="+2">Funny String</font></u></b></summary>
<br/>
  
*Problem :* https://www.hackerrank.com/challenges/funny-string/problem
  
 > If we need to compare between two arrays/string with the reserved version of this array , think about looping the array for the index 0 , and index (length -1 ), also if we have one condition that or one letter tells us the result, then return inside the for loop to prevent completing the loop and save execution time

**My solution :**

```js
    const arr = s.split("")
    for (let i =0 ; i
        const diff = arr[i].charCodeAt() - arr[i+1].charCodeAt()
        const diff2 = arr.at(-1*(i+1)).charCodeAt() - arr.at(-1*(i+2)).charCodeAt()
        if (Math.abs(diff)  !==  Math.abs(diff2)) return "Not Funny"
    }
    return "Funny"
```

**steps :-**  
1- convert the string to array

2- loop on this array

3- get the difference between first 2 letters  

4- get the difference between last 2 letters // reversed

5- get the absolute diff between the two diff

6- if not equal return " Not Funny"

</details>

##

<details>
 <summary id="alternating-characters"><b><u><font size="+2">Alternating Characters</font></u></b></summary>
<br/>
    
**Problem :** https://www.hackerrank.com/challenges/alternating-characters/problem

> if we need just a count , think about the length , also if we need to execute some operation of any sequence of characters inside a string the `regex` and `replaceAll` are very powerful tools

**My solution :**

```js
const clearString = s.replaceAll(/[A]+/g, "A").replaceAll(/[B]+/g, "B");
return s.length - clearString.length;
```

**steps :-**  
1- replace all repeated "A" with only one letter "A" and all repeated "B" with only one letter "B" , now I have the final string (the good one)

2- get the difference of the length to know how many character should I remove

</details>

##

<details>
 <summary id="string-construction"><b><u><font size="+2">String Construction</font></u></b></summary>
<br/>
  
  
 **Problem :** https://www.hackerrank.com/challenges/string-construction/problem

> if we need to count a unique characters , think about the Set

**NOT my solution :**

```js
return new Set(s.split("")).size;
```

**steps :-**  
1- in this problem they need to count cost of any additional character which is not in the string we are trying to build, so in other words need to get any unique addition so if we have "aa" string it will cost 1$ , if we have "ababo" , it will cost 3$ and so on

</details>

##

<details>
 <summary id="two-strings"><b><u><font size="+2">Two Strings</font></u></b></summary>
<br/>

**Problem :** https://www.hackerrank.com/challenges/two-strings/problem?isFullScreen=true

> Try to save looping times

**my solution :**

```js
const arraySet = [...new Set(s1.split(""))];
return !!arraySet.find((c) => s2.includes(c)) ? "YES" : "NO";
```

**steps :-**  
1- get all unique chars in s1 in array

2- find function get the first element match the condition so no need to loop on the others chars

  </details>

##

<details>
  <summary id="game-of-thrones"><b><u><font size="+2">Game of Thrones - I</font></u></b></summary>
  <br/>

**Problem :** https://www.hackerrank.com/challenges/game-of-thrones/problem

> if we have semantic string , think about using %

**my solution :**

```js
const count = {};
s.split("").forEach((c) => {
  count[c] ? (count[c] = count[c] + 1) : (count[c] = 1);
});
const freq = Object.values(count);
return freq.filter((c) => c % 2 !== 0).length > 1 ? "NO" : "YES";
```

**steps :-**  
1- I get the count of each character because we need to have only one odd number of characters

2- check if we have more than one or not

  </details>

##

<details>
  <summary id="strange-counter"><b><u><font size="+2">Strange Counter</font></u></b></summary>
<br/>

**Problem :** https://www.hackerrank.com/challenges/strange-code/problem?isFullScreen=true

> some time using two pointer is very good solution

**my solution :**

```js
let start = 1;
let end = 3;
let n = 1;
while (t > end) {
  n++;
  start = end + 1;
  end = end + [...Array(n - 1).keys()].reduce((t, v, i) => t * 2, 3);
}
const head = [...Array(n - 1).keys()].reduce((t, v, i) => t * 2, 3);
return head - (t - start);
```

**steps :-**  
1- I created two pointer for the start and end values n which is number of loops

2- while the time is not between the two pointers it means we should keep looping

3- update the start and end pointer adn increase the number of loops

note : to calculate the head of the loop I used this formula `[...Array(n-1).keys()].reduce((t, v, i) =>t*2 , 3)`

4-the value should be the head - the different between the time and the start pointer

</details>


## :smiley_cat: Author

- [@minaibrahimsaid](https://github.com/minaibrahimsaid/)

Made with &nbsp;❤️&nbsp;
