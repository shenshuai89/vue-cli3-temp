<template>
  <div class="home">
    <HelloWorld @send-msg="onsendMsg" :msg=msg name="homePage"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop, Watch } from "vue-property-decorator";
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
@Component({
  components: {
    HelloWorld
  }
})
export default class Home extends Vue {
  private msg:string = "this is home page"
  private onsendMsg(val:string){
    this.msg = val
  }
}
</script>
