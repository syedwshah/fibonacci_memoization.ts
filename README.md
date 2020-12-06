# fibonacci_memoization.ts
TS implementation of fibonacci memoization
```
interface Memo {
  [key: number]: number;
}

//Cache of fibonacci sequence
const cacheMeOusside: Memo = {};

const fib = (num: number, memo: Memo): number => {
  if (num < 0) {
    return 0;
  }
  else if (num <= 1) {
    memo[num] = num;
    return memo[num];
  }
  
  if (memo[num]) {
    return memo[num];
  }

  return fib(num - 1, memo) + fib(num - 2, memo);
}

// Sample output
const cache: Memo = cacheMeOusside;
for (let i = 0; i <= 10; i++) {
  cache[i] = fib(i, cacheMeOusside);
}
console.log(cache);
```

Output:
```
{ '0': 0,
  '1': 1,
  '2': 1,
  '3': 2,
  '4': 3,
  '5': 5,
  '6': 8,
  '7': 13,
  '8': 21,
  '9': 34,
  '10': 55 }
```
