# small-icon-menu
tiny icon menu based on material icons and vue
mainly created for side crud buttons menu in lists or tree views.

## Props

| Prop     | Type    | Required | Default                     | Description                                      |
| -------  | ------- | -------- | --------------------------- | ------------------------------------------------ |
| icons    | array   | false    | ['add', 'delete', 'edit']   | Any icon from material icon library              |
| labels   | object  | false    | {'add' : 'Add', 'delete' : 'Delete', 'edit' : 'Edit' }   | key icon name, value label |
| iconSize | string  | false    | '16px'                      | Size of icons                                    |
| height   | string  | false    | 'auto'                      | Height of menu                                   |
| width    | string  | false    | 'auto'                      | Width of menu                                    |
| absolute | boolean | false    | false                       | Absolute position menu                           |
| top      | string  | false    | '0px'                       | Position menu from top                           |
| left     | string  | false    | '0px'                       | Position menu form left                          |
| border   | boolean | false    | false                       | Border on/off                                    |
| column   | boolean | false    | false                       | Column orientation of icons                      |

## Installation

Install the package from npm by running:

```
$ npm i small-icon-menu
```

## Usage

Import, register and place the component in your Vue app.
Don't forget to include the material icons css "https://fonts.googleapis.com/icon?family=Material+Icons"


```html
<template>
  <smalliconmenu :icons="['add', 'delete', 'edit]" @add="emits add event" @delete="emits delete event" @edit="emits edit event"/>
</template>
```

```js
import smalliconmenu from 'smalliconmenu'

export default {
  components: {
    smalliconmenu
  },
}
```