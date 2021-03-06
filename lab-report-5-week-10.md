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
Joe's implementation didn't account for the `<` and `>` signs. It shouldn't have counted as a link but Joe's put it as a link.
In order to fix this we should look at this method:
![joe's](photos/joebreak.png)
Before we set the openParen, we should check if there are any `<` signs in between the brackets and the parenthesis.

## Second Difference

File name: 41.md(692c692)

Mine gave back `[url &quot;tit&quot;]`

Joe's gave back `[]`

For this test Joe's implementation was correct. We found the right result the same way as last time. In this test they had
```
[a](url &quot;tit&quot;)
```
This should not count as a link because of the space between 'url' and the rest on the phrase inside the parenthesis.
In order to fix this we should look at the method:
![mine](photos/minebreak.png)
When we get the open and closed parenthesis, we should check if there are any spaces in between the two of them.

