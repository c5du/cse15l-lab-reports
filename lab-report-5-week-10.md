# Week 10 Lab Report

## How I found the test
Our team used diff on the results of our implementation and on Joe's implementation and was given back the differences in test results between the two. Then we compared the different results.  

## First Difference

File name: 201.md(230c230)

Mine had gave back: `[]`

And Joe's gave back: `[baz]`

For this test, our teams implementation was correct. We figured this out by looking at the 201.md test file and put it into [commonMark](https://spec.commonmark.org/dingus/) to see what the correct implementation was. In this test, they had
```
[foo]: <bar>(baz)

[foo]
```
Joe's implementation didn't account for the `<` and `>` signs. It shouldn't have counted as a link but Joe's put it as a link

## Second Difference

File name: 41.md(692c692)

Mine gave back `[url &quot;tit&quot;]`

Joe's gave back `[]`

For this test Joe's implementation was correct. We found the right result the same way as last time. In this test they had
```
[a](url &quot;tit&quot;)
```
This should not count as a link because of the `&` signs, but our implementation didn't check for them.

