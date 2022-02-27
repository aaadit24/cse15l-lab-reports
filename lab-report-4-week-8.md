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
