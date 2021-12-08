# vue-amplify-image-viewer 

vue-amplify-image-viewer allows you to render images stored in S3 bucket in your vue application created with vue3.

### NPM
```npm
npm i vue-amplify-image-viewer
```
## Usage
Make sure to have installed aws-amplify dependency and storage credentials setup already
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
 
## Props

| Name                   | Type       | Description                                                  | Default                                                                 |
| ---------------------- | ---------- | ------------------------------------------------------------ | ----------------------------------------------------------------------- |
| `imageurl` _required_          | `String`   | S3 bucket image key      | `""`                                                                    |
| `CloudFront`           | `String`   | if using CloudFront distribution, just pass the CloudFront url, eg `https://cloudfront.amazon`                        | ` `                                                             |
| `showLoading`  | `Boolean`   | To show a pulse animation before image loads              |           true       |
| `level`    | `String`   | Defines the level of retriction placed on the image eg, public                                                     |  
| `alt`             | `String`   |      Alt for image tag| | 
 
 
## Other Considerations
This is not an official plugin from [AWS](https://aws.amazon.com/).

 
