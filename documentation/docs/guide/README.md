# vue-amplify-image-viewer 

vue-amplify-image-viewer allows you to render images stored in S3 bucket in your vue application created with vue3.

### NPM
```npm
npm i vue-amplify-image-viewer
```
## Usage
```javascript
<template>
     <vue-amplify-image-viewer 
      :imageurl="'image.jpg'"                    
      :showLoading="true"                                      
                    
    ></vue-amplify-image-viewer>
</template>

 <script>
import vue-amplify-image-viewer from "vue-amplify-image-viewer";

export default {
  components: {
    vue-amplify-image-viewer,
  },
}
  </script>
 
```

## Documentation
A more detailed guide can be found [here](https://vueamplifyimageviewer.netlify.app/)

## Want to say thanks?
If this has been helpful, kindly share the link to other and a star on the github repo would be helpful too


## License
Licensed under MIT License. [Click](https://github.com/somteacodes/vue3-paystack/blob/master/LICENSE.md) for details.
```

## Props

| Name                   | Type       | Description                                                  | Default                                                                 |
| ---------------------- | ---------- | ------------------------------------------------------------ | ----------------------------------------------------------------------- |
| `buttonClass`          | `String`   | CSS class names for the button, to style the component       | `""`                                                                    |
| `buttonText`           | `String`   | Displayed text for the button                                | `"Pay Now"`                                                             |
| `publicKey` _required_ | `String`   | Public key from your paystack API                            |                                                                         |
| `email` _required_     | `String`   | required                                                     |  
| `firstname`             | `String`   |      | First name to be stored in your receipts|
| `lastname`             | `String`   |      | Last name to be stored in your receipts|
| `amount` _required_    | `Number`   | required                                                     |                                                                         |
| `reference` _required_ | `String`   | a randomly generated code, made up of characters and numbers |                                                                         |
| `currency`             | `String`   | required                                                     | `"NGN"`                                                                 |
| `onSuccess`            | `Function` |                                                              | `function() { console.log(response); }`                                 |
| `onCancel`             | `Function` |                                                              | `function() { console.log("payment closed"); }`                         |
| `channels`             | `Array`    |                                                              | `function() { return ["card", "bank", "ussd", "qr", "mobile_money"]; }` |
| `metadata`             | `Object`   |                                                              | `{   "custom_fields":[{"display_name":"Cart Items",  "variable_name":"Invoice ID", "value":209}] }`                                             |
| `label`                | `String`   |                                                              | `""`                                                                    |

## Metadata (optional)
The metadata prop is a good way to add additional information to information stored in your records.
The meta data is of a JSON type and it has a reserved objecy key called `custom_fields`, that when used correctly displays nicely in your stored receipts. 

Custom fields have 3 keys: `display_name`, `variable_name` and `value`. 
The display name will be the title for the value when displaying it on your receipts

An example is
```
"metadata":{
   "custom_fields":[
    {
      "display_name":"Country",
      "variable_name":"country_name",
      "value":"Nigeria"
    },
    {
      "display_name":"Cart Items",
      "variable_name":"cart_items",
      "value":"3 bananas, 12 mangoes"
    }
  ]
}

```
Custom fields used can be seen in your paystack dashboard
![Image](/images/metadata.png)


<!-- ## Data

| Name              | Type      | Description | Initial value |
| ----------------- | --------- | ----------- | ------------- |
| `hasScriptLoaded` | `boolean` |             | `false`       |

## Methods

### mountScript()

**Syntax**

```typescript
async mountScript(): Promise<unknown>
```

### payWithPaystack()

**Syntax**

```typescript
payWithPaystack(): void
``` -->

## Other Considerations
This is not an official plugin from [paystack](https://paystack.com/).

You should defintely check out the official [paystack](https://paystack.com/developers) documentation for more information
