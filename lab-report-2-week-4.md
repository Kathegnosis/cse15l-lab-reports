## Lab Report 2

## So, you wanna debug?
Good choice. Debugging is a required skill. Although, I don't see why anyone would WANT to debug (it's usually done out of necessity), but you do you.

I will be using examples from lab 3 to show you how my partner and I debugged.


## Pt 1: The "Out of Memory" Bug
### The Failure Inducing Input (file link)
To test our code, we made some files that would fail the code. [This test file caused the code to fail from running out of memory.](https://github.com/Kathegnosis/markdown-parser/commit/a2d772f7fc14f32ad42e42032ea0d47cb45376d1) 
### Bug Symptom
Running this file crashed on the following error:
![image](https://user-images.githubusercontent.com/88159129/164987192-5313d842-8d66-4cbf-a697-de8c95d85702.png)

### How we fixed it (code diff)
![image](https://user-images.githubusercontent.com/88159129/164987287-c1118f9b-9707-4f2c-a011-7c245e633483.png)
We added a flag that would signal the loop to end if the same index appeared twice.
<br>\
(Please see the "note" in the next step for why this bugfix also has some issues...)

### But why did that fix it? (relationship between symptom, bug, input)
The symptom told us our program ran out of memory. Having previous programming experience, we knew this was due to the program not having a point where it ends (the do-while loop continues forever). So, we set on a search to find what made it go on forever, and after comparing the test file to the code, we saw that the "current index" would never be the end index, because the "current index" was set by the last parantheses (the bug), and our file continued after that. Obviously, the next step was making it break, and we did this by signaling to end if the same index appeared twice.
<br>\
Note: this "fix" actually has some bugs in in as well. When there is only one link, it outputs the same link twice. Also, there was no need to make a flag. We fixed this in lab 4, and [now it can both end early and not output two links that are the same. We also didn't need the flag in this version, since we now used the indexOf functionality.](https://github.com/Kathegnosis/markdown-parser/commit/07cc85f0f62fa1e95c2dd2a9eb80c4f809af32f5)

## Pt 2: Incorrectly formatted links causing crashes (parantheses)
### The Failure Inducing Input (file link)
[This test file with an incorrectly formatted link caused our code to fail.](https://github.com/Kathegnosis/markdown-parser/commit/8bff09b459a0bda3d56d363fcbe1384c77c410fb#diff-1254e030e34860e8f749acc24f529e23dbbd4b3627a614dc86b43560551a64d1)

### Bug Symptom
Running our code on the test file resulted in the following error message:
![image](https://user-images.githubusercontent.com/88159129/164988506-5f39c550-a9bc-4525-8c8c-58f53f2ae17a.png)

### How we fixed it (code diff)
![image](https://user-images.githubusercontent.com/88159129/164988532-f31525a5-d2e8-491c-ac3a-c752596bf20c.png)
We added a condition to return early if the input didn't contain any parantheses.

### But why did that fix it? (relationship between symptom, bug, input)
The symptom told us the index "-1" was being given at some point in the code, causing it to crash. We found out this was because the indexOf function returns -1 if it does not find the specified string in the input, and our code incorrectly stored that -1 value (the bug). The fast way to fix this was to add an "if" condition to test if the file contained parantheses or not, which we did.

Note: I'm realizing that a better way to fix these bugs would have been to simply end if any of them returned -1, especially after fixing the "double link" issue in lab 4 (see pt 1's note). This would then also be able to handle correct links being mixed with incorrectly formatted links.

## Pt 3: Incorrectly formatted links causing crashes (brackets)
### The Failure Inducing Input (file link)
[This test file with an incorrectly formatted link caused our code to fail.](https://github.com/Kathegnosis/markdown-parser/commit/23094c6fd4f45a2ee4d1fc72607cb9d4c43e956f)

### Bug Symptom
Running our code on the test file resulted in the following error message:
![image](https://user-images.githubusercontent.com/88159129/164988506-5f39c550-a9bc-4525-8c8c-58f53f2ae17a.png)

### How we fixed it (code diff)
![image](https://user-images.githubusercontent.com/88159129/164988532-f31525a5-d2e8-491c-ac3a-c752596bf20c.png)
We added a condition to return early if the input didn't contain any brackets.

### But why did that fix it? (relationship between symptom, bug, input)
The symptom told us the index "-1" was being given at some point in the code, causing it to crash. We found out this was because the indexOf function returns -1 if it does not find the specified string in the input, and our code incorrectly stored that -1 value (the bug). The fast way to fix this was to add an "if" condition to test if the file contained brackets or not, which we did.

Note: I'm realizing that a better way to fix these bugs would have been to simply end if any of them returned -1, especially after fixing the "double link" issue in lab 4 (see pt 1's note). This would then also be able to handle correct links being mixed with incorrectly formatted links.
