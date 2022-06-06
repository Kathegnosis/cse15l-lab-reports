# Week 10 Lab Report 5

## How'd you find the failing tests?

I used vimdiff after directing the failed test results to textfiles. Then, I checked the differences and manually found the corresponding tests.


## Link for the failing tests, please?

Test 495. https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/495.md


Test 567. https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/567.md



## What's wrong for the first test (495)?
It did not properly detect parentheses. 

### Who did it better?
My implementation had the incorrect output, while the given implementation was correct.


Below are the outputs for our implementations. Yours is on the left, mine is on the right.

![image](https://user-images.githubusercontent.com/88159129/172076116-1603b0e7-1f2a-4b2e-966f-32cade4c6929.png)

### What's the correct output?
[foo(and(bar))] 


### How to fix?
Currently, my program isn't detecting any extra closing parentheses. It simply ends once it sees the next closing parentheses. I think I could fix this by using the 'last' index for everything that closes before the next opening paren.

I would add extra code around here:


![image](https://user-images.githubusercontent.com/88159129/172076424-076abf9b-6460-4a96-bbd9-2cc1d34140d5.png)





## What's wrong for the second test (567)?

It incorrectly detected a link with spaces in it as a link.


### Who did it better?
My implementation had the incorrect output, while the given implementation was correct.


Below are the outputs for our implementations. Yours is on the left, mine is on the right.

![image](https://user-images.githubusercontent.com/88159129/172076302-be829954-cee0-43b3-a534-09a967fd3965.png)


### What's the correct output?

[]

### How to fix?

The issue is that I'm marking links with spaces in them as links, which is incorrect behavior. Links should not be detected if there are spaces within them.
The simplest way to fix this is to simply add a flag for spaces in the area between the first open bracket and the next closing bracket. 

I would add the flag here, after I found the indexes of []. I'd check in between them:
![image](https://user-images.githubusercontent.com/88159129/172076454-c29318a7-ffa5-4445-82f6-fcb81f1c3a29.png)


