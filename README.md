# prompt
A beautiful command-line prompt for node.js

## Install

```
npm install @hooked74/prompt
```

## API

All API methods have an optional options argument. Options has the following fields:
- answer <String|Boolean> Transmit a answer that will be automatically printed. There will be no user interaction, the answer will be immediately returned.
- default <String|Number|Boolean|Array|Function> Default value(s) to use if nothing is entered, or a function that returns the default value(s). If defined as a function, the first parameter will be the current inquirer session answers.
- validate <Function> Receive the user input and answers hash. Should return true if the value is valid, and an error message (String) otherwise. If false is returned, a default error message is provided.
- filter <Function> Receive the user input and return the filtered value to be used inside the program. The value returned will be added to the Answers hash.
- transformer <Function> Receive the user input, answers hash and option flags, and return a transformed value to display to the user. The transformation only impacts what is shown while editing. It does not modify the answers hash.
- when <Function|Boolean> Receive the current user answers hash and should return true or false depending on whether or not this question should be asked. The value can also be a simple boolean.
- pageSize <Number> Change the number of lines that will be rendered when using list, rawList, expand or checkbox.
- prefix <String> Change the default prefix message.
- suffix <String> Change the default suffix message.

### promptList(message, choices[, options])
- message <String> The question to print. If defined as a function, the first parameter will be the current inquirer session answers. Defaults to the value of name (followed by a colon).
- choices <Array> Array values can be simple numbers, strings, or objects containing a name (to display in list), a value (to save in the answers hash) and a short (to display after selection) properties.
- options <Object>
- @return <Promise<answer=String>> Answer selected by the user and wrapped in promise.

### promptCheckbox(message, choices[, options])
- message <String> The question to print. If defined as a function, the first parameter will be the current inquirer session answers. Defaults to the value of name (followed by a colon).
- choices <Array> Array values can be simple numbers, strings, or objects containing a name (to display in list), a value (to save in the answers hash) and a short (to display after selection) properties.
- options <Object>
- @return <Promise<answer=String>> Answer selected by the user and wrapped in promise.

### promptConfirm(message[, options])
- message <String> The question to print. If defined as a function, the first parameter will be the current inquirer session answers. Defaults to the value of name (followed by a colon).
- options <Object>
- @return <Promise<answer=Boolean>> Answer selected by the user and wrapped in promise.

### promptInput(message[, options])
- message <String> The question to print. If defined as a function, the first parameter will be the current inquirer session answers. Defaults to the value of name (followed by a colon).
- options <Object>
- @return <Promise<answer=String>> Answer selected by the user and wrapped in promise.
