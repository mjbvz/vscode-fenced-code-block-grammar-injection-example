# VSCode Markdown Fenced Code Block Grammar Injection Example

Demonstrates how an extension can inject support for a new grammar in VSCode's builtin markdown grammar for fenced code blocks. This extension injects an alias for JavaScript called `superjs` so support editor highlighting of blocks that look like:


~~~markdown
```superjs
someJsCode
```
~~~


Requires a VSCode build from April 12, 2017+
