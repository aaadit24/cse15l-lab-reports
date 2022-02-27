# Week 8 Lab report 3

## A link to your markdown-parse repository and a link to the one you reviewed in week 7
- My Repository : https://github.com/aaadit24/markdown-parse
- Repository Reviewed : https://github.com/maotcha/markdown-parse

## Decide on what it should produce by using either VScode preview or the CommonMark demo site
### CommonMark Demo Expected

``` 
[a link](url.com)

another link`

cod[e

code] 
```

## Showing the code in MarkdownParseTest.java for how you turned it into a test

```
@Test
public void snippet1() {
  String str = "`[a link`](url.com)" + "[another link](`google.com)`" + "[`cod[e`](google.com)" + "[`code]`](ucsd.edu)";
  assertEquals( "Validate MarkdownParse on snippet 1", List.of(""google.com", "ucsd.edu"), MarkdownParse.getLinks(str));
}
```

## For your implementation, the corresponding output when running the tests; if it passed, say so. If it didn’t pass, show the specific part of the JUnit output that shows the test failure.

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

## For the implementation you reviewed in Week 7, the corresponding output when running the tests; if it passed, say so. If it didn’t pass, show the specific part of the JUnit output that shows the test failure.

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

## Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.

Yes, We could search for search for backticks within links. If a backtick is found be can ignore that link and move on the to next
