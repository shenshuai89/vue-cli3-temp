<template>
  <div class="hello">
    <h1>{{ msg }}---{{name}}--{{getName}}</h1>
    <p>{{initNum}}</p>
    <button @click="add">给数字加1</button>
    <p>{{msg}}</p>
    <button @click="sendMsg">改变msg</button>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue, Watch, Emit } from 'vue-property-decorator';

@Component
export default class HelloWorld extends Vue {
  // props
  @Prop() private msg!: string;
  @Prop() private name!: string;

  // data
  private initNum: number = 0;
  //computed 使用get set函数
  get getName(){
    return this.name+"**computed"
  }
  // watch
  @Watch("msg")
  changeName(newV:string, oldV:string){
    console.log(`change txt: ${oldV} to ${newV}`)
  }
  // 生命周期
  created(){
    console.log("created阶段");
  }

  // methods
  private add(){
    this.initNum ++;
  }
  private changeMsg(){
    this.msg = "this is new msg"
  }
  @Emit()
  private sendMsg(msg:string):string{
    console.log("sendmsg");
    msg = "father"
    return "this is send to father message"
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
