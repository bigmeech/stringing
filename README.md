# stringing

Generate random string with custom dictionary if you want to use a custom dictionary, just follow the rules. It's Fast, simple and lightweight.

**You are be able to change percent of usage any part of your dictionary.**

## Installation

with NPM:

`npm i stringing`

## Usage

- [stringing.generate](#stringing.generate)
- [stringing.unique](#stringing.unique)

#### in Node.js

```javascript
var stringing = require('stringing');
```

#### in browser

You should use the browserified version in built directory

```html
<script src='built/stringing.min.js'></script>
<script>
  // Everything is ready
  // Do what you want to do
</script>
```

### stringing.generate

Generating random string:

`stringing.generate(option, length, dictionary);`

#### option

Type: `Object`, Optional.

Default:

```
{
  number: 1,
  lower: 1,
  upper: 1,
  symbol: 1
}
```

Your object must includes one part of your dictionary at least.

You can change the percent usage of any part of your dictionary through increasing or decreasing the number of the part.

for comprehension see [examples](#examples).

#### length

Type: `Number`, Optional.

Default: `10`

length of your string.

#### dictionary

Type: `Object`, Optional.

Default:

```javascript
{
  lower: 'abcdefghijklmnopqrstuvwxyz',
  upper: 'ABCDEFGHIJKLMNOPQRSTUVWXYZ',
  number: '1234567890',
  symbol: `~!@#$%^&*()_+.,<>?;'[]{}"|`
}
```

If you want use another dictionary or unique symbols or anything that you want, you can create your own dictionary and pass it.

for comprehension see [examples](#examples).

### stringing.unique

Generating unique string:

`stringing.unique(length)`

#### length

Type: `Number`, Optional.

Default: `10`

length of your string.

## Examples

```javascript
var stringing = require('stringing');

stringing.generate();
// '9R*uw&>UZ6'

stringing.generate({
  number: 20,
  lower: 2,
  upper: 1
}, 20);
// '9imfr8c459IC8389378D' - Number is more

stringing.generate({ uniqueWords: 1, number: 10 }, 20, {
  uniqueWords: 'JS-Node-_something',
  number: '123'
});
// 'in23hotgNd-es_-'

stringing.unique();
// '15245c059c'

stringing.unique(25);
// '15245c0da428bc9192c105615'
```

## Contributing, Idea, Issue

Feel free to fill an issue or create a pull request, I'll check it ASAP.

Just remember, lint and build your code:

`gulp lint build`

## LICENSE

MIT
