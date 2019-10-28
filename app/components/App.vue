<template>
    <Page 
      actionBarHidden="true"
      backgroundSpanUnderStatusBar="true"
      androidStatusBarBackground="#fff">
        <ClassComponent msg="This is a Class Component.ts" class="message" />
    </Page>
</template>

<script lang="ts">
import {Vue, Component, Prop} from 'vue-property-decorator';
import ClassComponent from './ClassComponent.vue';

const app = require("application");
const platform = require("platform");

@Component({
  components: {
    ClassComponent
  }
})
export default class App extends Vue {
    pageLoaded() { 
      var View = android.view.View;
      if (app.android && platform.device.sdkVersion >= '21') {
        var window = app.android.startActivity.getWindow();
        window.setStatusBarColor(0x000000);
        var decorView = window.getDecorView();
        decorView.setSystemUiVisibility(
          View.SYSTEM_UI_FLAG_LAYOUT_STABLE
          | View.SYSTEM_UI_FLAG_LAYOUT_HIDE_NAVIGATION
          | View.SYSTEM_UI_FLAG_LAYOUT_FULLSCREEN
          | View.SYSTEM_UI_FLAG_HIDE_NAVIGATION
          | View.SYSTEM_UI_FLAG_FULLSCREEN
          | View.SYSTEM_UI_FLAG_IMMERSIVE_STICKY);
      }
    }

    mounted() {
      this.pageLoaded()
    }
}
</script>

<style scoped>
    .message {
        vertical-align: center;
        text-align: center;
        font-size: 20;
        color: #333333;
    }
</style>
