# Test 1

## Show a screenshot of the code change diff from Github

![image](https://user-images.githubusercontent.com/97692709/151885844-65d0c4ad-2598-40e1-8c0d-1afcbda0a687.png)

## Link to the test file for a failure-inducing input that prompted you to make that change

[Link to test file](https://github.com/aaadit24/markdown-parse/blob/main/test-file.md)


## Show the symptom of that failure-inducing input by showing the output of running the file at the command line for the version where it was failing (this should also be in the commit message history)

![image](https://user-images.githubusercontent.com/97692709/151886312-14d4accb-2c4a-4745-a03a-86063e3c8c4b.png)

## Write 2-3 sentences describing the relationship between the bug, the symptom, and the failure-inducing input.

When there was an extra line after the last given link, the output would result in an infinite loop. We realized that when there was en empty line the value of nextOpenBracket would be -1, whcih was always less than the current index resulting in an infinte while loop

# Test 2

## Show a screenshot of the code change diff from Github

![image](https://user-images.githubusercontent.com/97692709/153675128-3f92e4de-57a3-4f9f-a78c-52aa5fd784d8.png)

## Link to the test file for a failure-inducing input that prompted you to make that change

[Link to test file](https://github.com/aaadit24/markdown-parse/blob/main/test-file2.md)


## Show the symptom of that failure-inducing input by showing the output of running the file at the command line for the version where it was failing (this should also be in the commit message history)

![image](https://user-images.githubusercontent.com/97692709/153675304-f8fbd6b3-6482-4bb0-a31a-8ea611489b6a.png)

## Write 2-3 sentences describing the relationship between the bug, the symptom, and the failure-inducing input.

the "(" was not immediately after "]", but the program did not check that. Resulting in the text inside curved brackets that is not immediately after the square brackets to be added to the list of links and be displayed.

# Test 3

## Show a screenshot of the code change diff from Github

![image](https://user-images.githubusercontent.com/97692709/153678306-3c4ace28-ef9a-4c1c-9712-60573f51df0f.png)

## Link to the test file for a failure-inducing input that prompted you to make that change

[Link to test file](https://github.com/aaadit24/markdown-parse/blob/main/test-file3.md)

## Show the symptom of that failure-inducing input by showing the output of running the file at the command line for the version where it was failing (this should also be in the commit message history)

![image](https://user-images.githubusercontent.com/97692709/153678470-bb306a07-06d1-42f4-841d-41a61cd73ed4.png)

## Write 2-3 sentences describing the relationship between the bug, the symptom, and the failure-inducing input.

Since there was no ")" the value of closeParam is -1, resulting in an error when ``` toReturn.add(markdown.substring(openParen + 1, closeParen)); ``` is called since -1 cannout be a parameter in substring. Therefore, when the code was run ``` StringIndexOutOfBoundsException ``` was thrown.
