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