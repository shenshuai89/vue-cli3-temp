<template>
  <div class="about">
    <h1>This is an about page</h1>
    <HelloWorld :msg=msg @sendMsg="sendMsgAbout" name="aboutPage"/>
  </div>
</template>
<script lang="ts">
import { Component, Vue, Prop, Watch} from 'vue-property-decorator';
import HelloWorld from '@/components/HelloWorld.vue';
@Component({
  components:{
    HelloWorld,
  }
})
export default class About extends Vue{
  private initNum:number = 0;
  private msg:string = "this is about page"

  private sendMsgAbout(val:string){
    this.msg = val
  }
}
</script>
