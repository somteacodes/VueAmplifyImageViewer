<script>
import { defineComponent } from 'vue';
 import {Storage} from "aws-amplify";
export default /*#__PURE__*/defineComponent({
  name: 'vue-amplify-image-viewer', // vue component name
   props: {
    imageurl:{
      type: String,
      default:""
    },
    showLoading:{
      type:Boolean,
      default:true
    },   
    cloudFront:{
      type:String,
      default:""
    },   
    level:{
      type:String,
      default:"public"
    },
  
    alt:{
      type:String,
      default:""
    }

  },
  data() {
    return {
      imageURL: null,
      loading:null,
      
    };
  },
  mounted() {
    this.loading=this.showLoading
      this.getImageURL()
  },
  methods: {
    async getImageURL() {
      if(this.cloudFront){ 
          this.imageURL = `${this.cloudFront}/${this.imageurl}`;    
          this.loading=false;
          return     
      }else{
        // use aws storage
        this.imageURL  = await Storage.get(this.imageurl, { level: this.level });
        this.loading=false;
        return
      } 
    },
  },
});
</script>

<template>
  <div>
    <div v-if="loading" class="loading">

    </div>
    <img :src="imageURL" :alt="alt"  
    style="height:100%; width:100%"
      />
  </div>
</template>
 

<style scoped>
.loading{
  background:#c7c7c7;
  width: 100%;
  height: 100%;
  animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

@keyframes pulse {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: .5;
  }
}
</style>
