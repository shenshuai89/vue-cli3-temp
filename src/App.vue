<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld :msg=msg @send-msg="onsendMsg" name="App-props-name" />
      {{count}}
    <button @click="addCount">给count加100</button>
    <p>------------------------------******下面为路由的信息******---------------------------------</p>
    <router-view></router-view>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop, Watch } from 'vue-property-decorator';
import HelloWorld from './components/HelloWorld.vue';

@Component({
  components: {
    HelloWorld,
  }
})
export default class App extends Vue {
  private count:number = 0;
  private msg:string = "Welcome to Your Vue.js + TypeScript App"

  created() {
    console.log("app中的created生命周期"); 
  }

  private addCount(){
    this.count += 100
  }
  private onsendMsg(str:string):void{
    this.msg = str;
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
