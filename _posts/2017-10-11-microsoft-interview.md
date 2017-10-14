---
layout: post
title: Interview with Microsoft
---

I had an interview today with one of [tech's frightful five](https://www.nytimes.com/2017/05/10/technology/techs-frightful-five-theyve-got-us.html): Microsoft. It was a 30 minute interview held in the [Career Services](https://careers.unl.edu/) office of the Nebraka Student Union. I was first contacted about two weeks prior by a **U.S. Region Talent Sourcer at Microsoft** via Linkedin:

![linkedin-message]({{site.url}}/assets/img/linkedin-microsoft-interview.png)
 
Sounds innocuous, but this recruiter didn't even have a profile picture, so I was a little hesitant to hand over a resume containing personal information. I did so in faith and two days later I received a confirmation email from Microsoft University Recruiting (*microsoft@yello.co* domain) containing an invitation to schedule an interview time that worked best for me. I was pretty excited to interview with such a prestigous tech company and I was advised to be prepared for technical questions.

![microsoft-interview-prep]({{site.url}}/assets/img/microsoft-interview-prep.png)

Apparently, the first interview is just to assess your fit for Microsoft and not for a specific position or team. I like that philosophy, it's a bit foreign to me but I can see how it allows employees the option to thrive in areas they are passionate about. Of course I don't think all companies can afford this luxury. Maybe it's one of the perks of being a tech giant? A way to leverage the acquisition of top talent? (I'm not making any claims thatthis includes me).

To help prep for the interview, I was directed to their [student career portal](https://careers.microsoft.com/students). However, even though I knew the interview process would likely contain whiteboard questions, I can honestly say I did ZERO preparation. I'm debating if that was a mistake or not as I'm not convinced studying algorithms would have helped me to answer the specific questions I was asked, but I know it certainly wouldn't have hurt :) I just wasn't willing to take any significant time away from my courses. So I decided to march in there as-is. On to the interview!

After several minutes of small talk which included my educational background and future goals, the recruiter got right into the first question.

1) Imagine you are given an array as follows:

```Javascript
[A,B,...,Z,AA,AB,...AZ,BA,BB,...,BZ,...,ZA,ZB,...ZZ,AAA,AAB,... and so on ...]
```

Given that this pattern continues indefinitely, write a function which takes a positive integer and returns the string of letters (call it the title) at that index. For example,

```Javascript
getTitle(1) = A,
getTitle(26) = Z,
getTitle(27) = AA,
getTitle(703) = AAA
```

Right away, I knew that if I was given an integer `x`, then `x mod 26` would give me the last digit. But I was a little stumped from here. How do I get the other digits? After contemplating silently for a minute I realized the problem space is in fact growing. There are 26 one letter titles (A-Z), but there are 26^2 = 676 two letter titles (AA-ZZ). So then I knew that if I calculated `Log(x)/Log(26)` it would essentially give me how many letters I have. For example `Log(703)/Log(26) ~ 2.012` so I knew it had two letters in front and the third letter would be `703 mod 26 = 1 => A`. After what felt like an eternity of struggle, the recruiter must have taken pity on me and explained that I was on the right track by taking the modulus and finding the remainder, but that I needed to continue this process iterativley. So for example:

`703 = 26*27 + 1`,
`27 = 26*1 + 1`,
`1 = 26*0 + 1`

Reading off the remainders at each step we get `{1,1,1} => AAA`. Once he showed this to me I immediatley recognized it as being an application of the [Euclidean Algorithm](https://en.wikipedia.org/wiki/Euclidean_algorithm#Procedure). I had learned this algorithm in the context of finding the greatest common divisor between two integers. But in a sense it also offers a way to represent a number in terms of a different base. In our case we can represent `703(base 10)` as `111(base 26)` because `703 = 1*26^2 + 1*26^1 + 1*26^0`. Essentially, as we progress from A up to Z we are just counting in base 26! A very cool problem indeed. I coded up the solution in Javascript tonight after getting home.

```javascript
function getTitle (x) {
  let alphabet = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('');
  let n = alphabet.length;
  let title = '', q, r;
  do {
    q = Math.trunc(x/n);
    r = x % n;
    title = alphabet[r-1].concat(title);
    x = q;
  } while (q != 0);
  return title;
}
console.log(getTitle(703));// AAA
```

The recruiter did ask me a second question about how to sort the given array:

`[1,3,9,17,200,39,12,7,2]`

and how we should test if a particular element is in the array. The key to this data is that it's unimodal. The data increases and then decreases. So there are already two ordered subsets of this data. I [suspect](https://web.stanford.edu/class/archive/cs/cs161/cs161.1138/lectures/06/Small06.pdf) we use a divide and conquer-like algorithm to sort this list. Once it's sorted we could use a binary search algorithm to test for a specific data point or perhaps use something like a [bloom filter](https://sagi.io/2017/07/bloom-filters-for-the-perplexed/) if we only need a probabilistic handle on set membership. Unfortunately, we didn't have the time to discuss a solution to this in much detail.

After everything was over I did have remorse about not being able to answer the questions completely. On the whole it was a great growing experience and my first time interviewing with a large tech company. In the future I will prepare a bit more. I found a nice [interview checklist](https://github.com/yangshun/tech-interview-handbook/blob/master/preparing/cheatsheet.md) on github and a blog full of good [questions to ask](https://cternus.net/blog/2017/10/10/questions-i-m-asking-in-interviews-2017/) potential employers.