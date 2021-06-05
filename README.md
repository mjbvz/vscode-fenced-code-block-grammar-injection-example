# VSCode Markdown Fenced Code Block Grammar Injection Example

Demonstrates how an extension can inject support for a new grammar in VSCode's builtin markdown grammar for fenced code blocks. This extension injects an alias for JavaScript called `superjs` so support editor highlighting of blocks that look like:


~~~markdown
```superjs
someJsCode
```
~~~


## Structure

- `package.json` - VS Code extension manifest file. The `contributes.grammars` section registers the injected grammar.
- `syntaxes/codeblock.json` - The injected grammar itself

## How to modify this repo to support a new language in fenced code blocks 

1. In `syntaxes/codeblock.json`, change the `begin` rule from `superjs` to the identifier of your target language. This identifier is what people will write in markdown.
2. In `syntaxes/codeblock.json`, change the inner `include` rule from `"source.js"` to the scope of your target language. This scope can be found by looking at the target language's grammar.
3. In `syntaxes/codeblock.json`, change the `contentName` from using `superjs` to using a identifier for your language. This identifier may only contain letters but does not have to match the identifier from step 1.
4. In `syntaxes/codeblock.json`, change the `scopeName` from using `superjs` to using a identifier for your language. This identifier may only contain letters but does not have to match the identifier from step 1.
5. In `package.json`, change the `scopeName` to match the scopeName from step 4.
6. In `package.json`, change `embeddedLanguages` to map between the `contentName` from step 3 and the VS Code identifier for your language.
7. In `package.json`, change the `id` from using `superjs-injection` to using an identifier for your grammar injection. This identifier does not have to match the identifier from step 1.
8. In `package.json`, change the `language` from using `superjs-injection` to using an identifier for your grammar injection. This identifier has to match the identifier from step 7.
