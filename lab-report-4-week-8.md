# Week 8 Lab report 3

### A link to your markdown-parse repository and a link to the one you reviewed in week 7
- My Repository : https://github.com/aaadit24/markdown-parse
- Repository Reviewed : https://github.com/maotcha/markdown-parse

## Snippet 1
### Decide on what it should produce by using either VScode preview or the CommonMark demo site
``` 
[a link](url.com)

another link`

cod[e

code] 
```

### Showing the code in MarkdownParseTest.java for how you turned it into a test

```
@Test
public void snippet1() {
  String str = "`[a link`](url.com)" + "[another link](`google.com)`" + "[`cod[e`](google.com)" + "[`code]`](ucsd.edu)";
  assertEquals( "Validate MarkdownParse on snippet 1", List.of(""google.com", "ucsd.edu"), MarkdownParse.getLinks(str));
}
```

### For your implementation, the corresponding output when running the tests; if it passed, say so. If it didn’t pass, show the specific part of the JUnit output that shows the test failure.

```
JUnit version 4.13.2
.......E.........
Time: 0.008
There was 1 failure:
1) snippet1(MarkdownParseTest)
java.lang.AssertionError: Validate MarkdownParse on snippet 1 expected:<[google.com, ucsd.edu]> but was:<[url.com, `google.com, google.com]>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at MarkdownParseTest.snippet1(MarkdownParseTest.java:169)

FAILURES!!!
Tests run: 16,  Failures: 1
```

### For the implementation you reviewed in Week 7, the corresponding output when running the tests; if it passed, say so. If it didn’t pass, show the specific part of the JUnit output that shows the test failure.

``` 
JUnit version 4.13.2
...E..
Time: 0.007
There was 1 failure:
2) snippet1(MarkdownParseTest)
java.lang.AssertionError: Validate MarkdownParse on snippet 1 expected:<[google.com, ucsd.edu]> but was:<[url.com]>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at MarkdownParseTest.snippet1(MarkdownParseTest.java:65)

FAILURES!!!
Tests run: 1,  Failures: 1
```

### Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.

Yes, We could search for search for backticks within links. If a backtick is found be can ignore that link and move on the to next

## Snippet 2
### Decide on what it should produce by using either VScode preview or the CommonMark demo site
``` 
[a nested link](b.com)

a nested parenthesized url

some escaped [ brackets ]
```

### Showing the code in MarkdownParseTest.java for how you turned it into a test

```
@Test
public void snippet2() {
    String snippet = "[a [nested link](a.com)](b.com)" +"[a nested parenthesized url](a.com(()))" + "[some escaped \\[ brackets \\]](example.com)";
    assertEquals(
        "Validate MarkdownParse on snippet 2", List.of("a.com", "a.com(())", "example.com"), MarkdownParse.getLinks(snippet)
    );
}
```

### For your implementation, the corresponding output when running the tests; if it passed, say so. If it didn’t pass, show the specific part of the JUnit output that shows the test failure.

```
JUnit version 4.13.2
.......E.E..........
Time: 0.008
There was 1 failure:

2) snippet2(MarkdownParseTest)
java.lang.AssertionError: Validate MarkdownParse on snippet 2 expected:<[a.com, a.com(()), example.com]> but was:<[a.com, a.com((]>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at MarkdownParseTest.snippet2(MarkdownParseTest.java:182)

FAILURES!!!
Tests run: 16,  Failures: 1
```

### For the implementation you reviewed in Week 7, the corresponding output when running the tests; if it passed, say so. If it didn’t pass, show the specific part of the JUnit output that shows the test failure.

``` 
JUnit version 4.13.2
..E..E.E...
Time: 0.006
There was 1 failure:

3) snippet2(MarkdownParseTest)
java.lang.AssertionError: Validate MarkdownParse on snippet 2 expected:<[a.com, a.com(()), example.com]> but was:<[a.com)](b.com]>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at MarkdownParseTest.snippet2(MarkdownParseTest.java:63)

FAILURES!!!
Tests run: 5,  Failures: 3
```

### Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change

No, there is a solution to this problem but it cannot be fixed within 10 lines. Thisis because there are way too many cases with  parentheses, brackets, and escaped brackets irregularities. Multiple loops and contitions are required to fix all the issues regarding this.

## Snippet 3
### Decide on what it should produce by using either VScode preview or the CommonMark demo site
``` 
[this title text is really long and takes up more than one line

and has some line breaks]( https://www.twitter.com )

this title text is really long and takes up more than one line

[this link doesn't have a closing parenthesis](github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/

)

And then there's more text
```

### Showing the code in MarkdownParseTest.java for how you turned it into a test

```
@Test
public void snippet3() {
    String snippet = "[this title text is really long and takes up more than " +"one line" +"and has some line breaks](" +"    https://www.twitter.com" +")" +
        "[this title text is really long and takes up more than " +"one line](" +"    https://ucsd-cse15l-w22.github.io/" +")" +
        "[this link doesn't have a closing parenthesis](github.com" + "And there's still some more text after that." +
        "[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/" +")" +"And then there's more text";

    assertEquals(
        "Validate MarkdownParse on snippet 3",List.of("https://ucsd-cse15l-w22.github.io/"), MarkdownParse.getLinks(snippet)
    );
}
```

### For your implementation, the corresponding output when running the tests; if it passed, say so. If it didn’t pass, show the specific part of the JUnit output that shows the test failure.

```
JUnit version 4.13.2
.......E.E.E.........
Time: 0.007
There was 1 failure:

3) snippet3(MarkdownParseTest)
java.lang.AssertionError: Validate MarkdownParse on snippet 3 expected:<[https://ucsd-cse15l-w22.github.io/]> but was:<[https://www.twitter.com, https://ucsd-cse15l-w22.github.io/, https://cse.ucsd.edu/]>
	at org.junit.Assert.fail(Assert.java:89)
	at org.junit.Assert.failNotEquals(Assert.java:835)
	at org.junit.Assert.assertEquals(Assert.java:120)
	at MarkdownParseTest.snippet3(MarkdownParseTest.java:206)

FAILURES!!!
Tests run: 17,  Failures: 1
```

### For the implementation you reviewed in Week 7, the corresponding output when running the tests; if it passed, say so. If it didn’t pass, show the specific part of the JUnit output that shows the test failure.

``` 
JUnit version 4.13.2
..E..E.E.E..
Time: 0.007
There was 1 failure:

4) snippet3(MarkdownParseTest)
java.lang.StringIndexOutOfBoundsException: begin 89, end -1, length 89
	at java.base/java.lang.String.checkBoundsBeginEnd(String.java:4601)
	at java.base/java.lang.String.substring(String.java:2704)
	at MarkdownParse.getLinks(MarkdownParse.java:26)
	at MarkdownParse.getLinks(MarkdownParse.java:35)
	at MarkdownParseTest.snippet3(MarkdownParseTest.java:90)

FAILURES!!!
Tests run: 5,  Failures: 1
```

### Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.

Yes, We could search for search for newlines within the title and links, that are within matching parentheses and brackets. 
