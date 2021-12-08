<script>
import { defineComponent } from 'vue';
import VueAmplifyImageViewer from '@/vue-amplify-image-viewer.vue';

export default defineComponent({
  name: 'ServeDev',
  components: {
    VueAmplifyImageViewer
  }
});
</script>

<template>
  <div id="app">
    <vue-amplify-image-viewer />
  </div>
</template>
