# How To Testcase?!?!
## Part 1: markdown-parse links
Link to my repository: https://github.com/Kathegnosis/markdown-parser


Link to the repository I'm reviewing: https://github.com/Pgerardocastaneda/markdown-parser 


## Part 2: failures 
Note: EVERY TEST FAILED. 

### My repository's failures
Snippet 1 Test (my repository)
![image](https://user-images.githubusercontent.com/88159129/169742800-af363b6b-98a0-449a-923e-85083dd028ef.png)

Snippet 2 Test (my repository)
![image](https://user-images.githubusercontent.com/88159129/169742867-d4d1f7d8-2cfe-4dbe-8936-698058baf2ee.png)

Snippet 3 Test (my repository)
![image](https://user-images.githubusercontent.com/88159129/169742923-10d057cf-b691-4c0b-be42-e9221e767eb4.png)


### Review repository's (pedro) failures
Snippet 1 Test (review repository)
![image](https://user-images.githubusercontent.com/88159129/169743200-20306b52-9de7-4fa6-88c8-5c77abf7f44a.png)

Snippet 2 Test (review repository)
![image](https://user-images.githubusercontent.com/88159129/169743232-b26464a1-1545-4f32-b098-03fec9771b56.png)

Snippet 3 Test (review repository)
![image](https://user-images.githubusercontent.com/88159129/169743278-a56e14e9-f1b1-4841-8016-c2190d251272.png)


## Part 3: Answering Questions
Answer the following questions with 2-3 sentences each:
* Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.


Yes, I could add an "if" statement for backticks. However, this would only apply to the 'text' part of the link (so before the brackets), and not the link itself that can have backticks. 


* Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change.


I think it would be a more involved change. I'm sure I could add an "if" statement to check for another opening parentheses following a previous one, and ignore it, with the same test for closing parentheses. However, I have not tried this, and there are a multitude of ways this could break so I would need to do thorough testing, along with it being bad practice to include links with parentheses in them. 


* Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.


Somewhat. I think I could ignore links with newlines in the text segment using an if statement. However, I am not sure how I would do it for links, since they could have a line break by coincidence.

