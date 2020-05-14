# Boiled Page assistive alert singleton and script

Assistive alert SCSS singleton and script for Boiled Page frontend framework. They are intended to create an invisible element where alerts can be pushed for assistive technologies.

## Install

Place `_assistive-alert.scss` file to `/assets/css/singletons` directory, and add its path to singleton block in `assets/css/app.scss` file. 

You will also need to place `assistive-alert.js` to `/assets/js` directory and add its path to `scripts` variable in `gulpfile.js` to be combined with other scripts.

## Usage

### Assistive alert component

#### Classes

Class name | Description | Example
---------- | ----------- | -------
`assistive-alert` | Applies assistive alert. | `<div class="assistive-alert"></div>`

#### Examples

##### Example 1

The following example shows an invisible element where alerts can be pushed for assistive technologies. `data-assistive-alert` attribute is used for assistive alert script.

```html
<div class="assistive-alert" data-assistive-alert></div>
```

### Assistive alert script

#### Usage

To initialize assistive alert, call `init()` method the following way:

```js
// Initialize assistive alert
AssistiveAlert.init({
  wrapper: document.querySelector('[data-assistive-alert]')
});
```

#### Methods

##### Initialize assistive alert

`init(options)` - Initialize assistive alert.

Parameter | Type | Required | Description
----------|------|----------|------------
`options` | Object | Yes | Options

Available properties for `options` object:

Option| Type | Default | Required | Description
------|------|---------|----------|------------
`wrapper` | Object | null | Yes | Element where the latest alert is pushed into.
`timeout` | Number | 7000 | No | A given number of milliseconds after alert will be destroyed.

##### Add alert

`add(alert)` - Add new alert to assistive alert's wrapper.

Parameter | Type | Required | Description
----------|------|----------|------------
`alert` | String | Yes | Content of alert.
