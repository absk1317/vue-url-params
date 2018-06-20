# vue-url-params

A vue mixin that simplifies working with url parameters. The package is developed for the purpose of allowing the key and values of a vue filter to be defined with url parameters It adds the params after a `?` and won't let the window reload.

## Install

**Public package installation**

You can install the package via npm:

```bash
$ npm install vue-url-params # using npm
$ yarn add vue-url-params # using yarn
```

## Usage

Import the package into your vue component.

```js
import vueUrlParameters from 'vue-url-params';
```

Apply the mixin:

```js
mixins: [vueUrlParameters],
```

Retrieve values from url on component init:

```js
// searchParams should be replaced with an object containing your properties
this.searchParams = this.getFiltersFromUrl(this.searchParams);
```

Trigger update of url hash when a filter changes, or in the method responsible for sending a request.

```js
this.updateUrlHash(this.searchParams);
```

**Example structure of an object (searchParams) that can be used with this package.**

```js
data() {
  return {
    searchParams: {
      q: null,
      type: 'all'
    }
  }
}
```

### Casting of attributes

When you fetch attributes from the url, you can pass in a second parameter to the `getFiltersFromUrl()` function in order to case the attributes automatically:

```js
this.getFiltersFromUrl(this.searchParams, true);
```

Strings that can be cast to a numeric value will be cast to a float. Strings that equals either _true_ or _false_ will be cast to a boolean.

## Security

If you discover any security related issues, please contact [absk1317@gmailc.com](mailto:absk1317@gmail.com) or use the issue tracker.

## Credits

- [Sempro](https://github.com/sempro)
