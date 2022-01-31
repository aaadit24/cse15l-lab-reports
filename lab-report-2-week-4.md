## Show a screenshot of the code change diff from Github

![image](https://user-images.githubusercontent.com/97692709/151885844-65d0c4ad-2598-40e1-8c0d-1afcbda0a687.png)

## Link to the test file for a failure-inducing input that prompted you to make that change

https://github.com/aaadit24/markdown-parse/blob/main/test-file.md

## Show the symptom of that failure-inducing input by showing the output of running the file at the command line for the version where it was failing (this should also be in the commit message history)

![image](https://user-images.githubusercontent.com/97692709/151886312-14d4accb-2c4a-4745-a03a-86063e3c8c4b.png)

## Write 2-3 sentences describing the relationship between the bug, the symptom, and the failure-inducing input.

When there was an extra line after the last given link, the output would result in an infinite loop. We realized that when there was en empty line the value of nextOpenBracket would be -1, whcih was always less than the current index resulting in an infinte while loop
