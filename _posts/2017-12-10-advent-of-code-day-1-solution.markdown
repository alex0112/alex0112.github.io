---
layout: post
title:  "Yay for map_cons"
date:   2017-12-10 03:37:00 -0700
categories: programming ruby
---

I wrote this function to meet the requirements of the [first advent of code challenge.][advent1]

```ruby:special_sum.rb
def special_sum(num)
  num
    .to_s
    .split('')
    .map {|e| e.to_i}
    .instance_eval { self.push(self[0]) }
    .each_cons(2).map { |set| set[0] if set[0] == set[1] }
    .compact
    .sum
end
```

This post is about my thought process getting there, how I did it wrong first,  and a feature I wish ruby had.

The problem is as follows:

*Write a function that sums all digits which  match the next digit in a list. The list is circular, so the digit after the last digit is the first digit in the list.*

For example:

- 1122 produces a sum of 3 (1 + 2) because the first digit (1) matches the second digit and the third digit (2) matches the fourth digit.
- 1111 produces 4 because each digit (all 1) matches the next.
- 1234 produces 0 because no digit matches the next.
- 91212129 produces 9 because the only digit that matches the next one is the last digit, 9.


# Doing it wrong first:

My intial attempt went something like this:
```ruby:special_sum.rb
def special_sum(num)
  num = num.to_s.split('').map {|e| e.to_i}

  sum_list = [0]

  sum_list.push num[0] if num[0] == num[-1]
  num.each do |i1, i2| ## SHOULD THIS BE each_slice?
    sum_list.push i1 if i1 == 12
  end

  return sum_list.sum
end
```

Which doesn't quite work.

If it doesn't seem untidy to you, it should.

The line `sum_list = [0]` first of all, is a messy way to handle data.  This was the list that would be summed at the end of the program, and so the rest of the function ends up being related to pushing elements to that list.  (There's only a zero in it because if no number is repeated consecutively, nothing will be pushed to the array, so the sum should be zero.  The fact that I need to explain it here is further evidence that the code is not well thought out.)

The biggest smell for me, is variable declaration at the beginning of a function.  A smell because we have a way to go about wrapping up data where it needs to go, and that's through objects.  Too much data handling at the beginning of a function may be a sign that proper abstraction may be needed elswhere.

Of course, for an operation that is essentially just a mathematical one, you can get away with using a data structure well.  Because functional programming. But more on that later.

The second not-so-great bit of this program is the line
```
sum_list.push num[0] if num[0] == num[-1]
```
which just says "If the first element and the last element are the same, append the first element to the end of the array."  Which logically is a clever way to handle the circularness we need from our list without actually building a true circular list.  Instead we can just generate a list which for the purposes of this puzzle is logically equivilant.

That's all fine and good.  But it's just so random in the function.  So far the function reads as if someone just stumbled through the problem and wrote a line that met the needs of the current aspect of the function as it came up.  Very much impromptu programming.

The final problem and Achilles Heel of this function is in the itterator:
```
num.each_slice(2) do |i1, i2|
    sum_list.push i1 if i1 == 12
  end
```

Simple right?  "Grab two elements, compare them, and if they're the same throw the element into the sum_list."  Right?  Not quite.
To understand the problem with this approach let's take a look at the following list:
```
[1, 1, 1, 2, 3, 5, 8, 7]
```
How would our `.each_slice(2)` method split this array up?  Well, like so:

```
[1, 1] [1, 2] [3, 5] [5, 7]
```
Which isn't quite what we want.  Because the second 1 is never compared to the third 1, 2 is never compared with 3, and the 5's are never compared with each other.  What we really need is our resulting array to look like this:

```
[1, 1] [1, 1] [1, 2] [2, 3] [3, 5] [5, 5] [5, 7]
```

As for how we get that array, let's look at the correct solution to the problem.

# A right way:

Introducing `.each_cons`.  A powerful way of treating our list as if it's a linked list.  And really for a history lesson we should talk about *lisp*.

There are three parts to a linked list:  the *car*, the *cons*, and the *cdr*.  



[advent1]: https://adventofcode.com/2017/day/1