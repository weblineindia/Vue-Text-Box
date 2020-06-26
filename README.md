# Vue Text Box Component

A Vue.js Text Box component specifies an input field where the user can enter data.

## Table of contents

- [Browser Support](#browser-support)
- [Demo](#demo)
- [Getting started](#getting-started)
- [Usage](#usage)
- [Available Props](#available-props)
- [Methods](#methods)
- [Want to Contribute?](#want-to-contribute)
- [Need Help / Support?](#need-help)
- [Collection of Components](#collection-of-components)
- [Changelog](#changelog)
- [License](#license)
- [Keywords](#Keywords)

## Browser Support

![Chrome](https://raw.github.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png) | ![Firefox](https://raw.github.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png) | ![Safari](https://raw.github.com/alrra/browser-logos/master/src/safari/safari_48x48.png) | ![Edge](https://raw.github.com/alrra/browser-logos/master/src/edge/edge_48x48.png) | ![IE](https://raw.github.com/alrra/browser-logos/master/src/archive/internet-explorer_9-11/internet-explorer_9-11_48x48.png) |
--- | --- | --- | --- | --- | --- |
83.0 ✔ | 77.0  ✔ | 13.1.1 ✔ | 83.0 ✔ | 11.9 ✔ |

## Demo

[![](input.gif)](https://github.com/weblineindia/Vue-Text-Box/input.gif)


## Getting started

Install the npm package:

``` bash
npm install vue-weblineindia-text-box
#OR
yarn add vue-weblineindia-text-box
```

## Usage

Use the `<vue-weblineindia-text-box>` component:

```vue
<template>
  <div>
    <InputComponent 
    :placeholder="placeholder" 
    :value="valueData" 
    @Change ="onChange"
     @focus="onFocus" 
     @blur="onBlur"
     />
  </div>
</template>
<script>
import InputComponent from 'vue-weblineindia-text-box'
export default {
   components: {
     InputComponent
   }
  data(){
    return{
      valueData :'',
      placeholder:'Input field'
    }
  },
  methods(){
    onFocus(event){
        event.target.placeholder = ''
    },
    onBlur(event){
        event.target.placeholder = this.placeholder
    },
    onChange(event ,value){
      this.valueData = value
    }
  }
}
</script>
```

## Available Props

| Prop | Type | default | Description |
| --- | --- | --- | --- |
| id | String |   |ID for the input |
| name | String |   |Nam for the input |
| value | string | | Value of the component |
| classname | object |   |  Class to the input |
| placeholder | String |   | The input field will get this placeholder text |
| hide | Boolean | false  | Hide component  |
| disabled | Boolean | false  | Disable component  |
| tabindex | Number | 0  | Tab index of the component  |
| maxlength | Number | 25  | The input maxlength  |
| regex | RegExp |  | The input regex  |
| autocomplete | String | off  | The input of autocomplelete  |
| type | String | text  | Type for the input  |

## Methods

| Name | Description |
| --- | --- |
| focus | Gets triggered when the autocomplete input field receives focus. |
| blur | Gets triggered when the autocomplete input field loses focus. |
| change | Gets triggered when the autocomplete results got changed. |
| keypress | Gets triggered when a key gets pressed. |
| keydown | Gets triggered when a key gets down. |


## Want to Contribute?

- Created something awesome, made this code better, added some functionality, or whatever (this is the hardest part).
- [Fork it](http://help.github.com/forking/).
- Create new branch to contribute your changes.
- Commit all your changes to your branch.
- Submit a [pull request](http://help.github.com/pull-requests/).

-----

## Need Help? 

We also provide a free, basic support for all users who want to use this VueJS Textbox Component in their software project. In case you want to customize this Textbox Component to suit your development needs, then feel free to contact our [VueJS developers](https://www.weblineindia.com/hire-vuejs-developer.html).

-----

## Collection of Components
We have built many other components and free resources for software development in various programming languages. Kindly click here to view our [Free Resources for Software Development](https://www.weblineindia.com/software-development-resources.html )

------

## Changelog

Detailed changes for each release are documented in [CHANGELOG.md](./CHANGELOG.md).

## License

[MIT](LICENSE)

[mit]: https://github.com/weblineindia/Vue-Text-Box/blob/master/LICENSE

## Keywords

vue-weblineindia-textbox,vue-weblineindia-text-box,textbox,input,vue components,vuejs,vuejs component
