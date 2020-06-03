---
title: Minimum to one, Dynamic Programming
tags: [dp, dynamic programming, minimum to one]
style: fill
color: success
description: Minimum steps to minimize n as per given condition.
---
## Minimum steps to minimize n as per given condition
Given a number n, count minimum steps to minimize it to 1 according to the following criteria:

- If n is divisible by 2 then we may reduce n to n/2.
- If n is divisible by 3 then you may reduce n to n/3.
- Decrement n by 1.

***


## code :

##### top-down approach.

```javascript


function m(n, dp){

	if(n==1){
		return 0;
	}

	if(dp[n]!== 0){
		return dp[n];
	}

	let op1, op2, op3;

	op1=op2=op3=4294967295;

	if(n%3 === 0){

		op1 = m(n/3, dp) + 1;
	}
	if(n%2 === 0){

		op2 = m(n/2, dp) + 1;
	}
	op3 = m(n-1, dp) + 1;

	let ans = Math.min(Math.min(op1,op2),op3);
	return dp[n] = ans

}



let dp = new Array(100)
	dp.fill(0,0,99)
console.log(dp)

let x = m(10, dp)
console.log(x)

```