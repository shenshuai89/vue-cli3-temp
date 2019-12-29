# vue2之使用Vue CLI3开发时初始化项目不同环境配置

## [vue-ts](https://github.com/shenshuai89/vue-cli3-temp/tree/vue-ts)

使用typescript书写vue项目代码
首先要引用

``` 
import { Component, Vue, Prop, Watch, Emit } from "vue-property-decorator";
@Component({
    components:[
        HelloWorld,
    ]
})
export default class Hi extends Vue{
  // data
  @Prop() private msg:string = "this is home page"

  // computed
  get comMsg(){
      return this.msg+" computed"
  }

  // watch
  @Watch()
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
  
  @Emit()
  private sendMsg():string{
    console.log("sendmsg");
    msg = "father"
    // 事件的返回值为传递的参数
    return "this is send to father message"
  }
}
```

## [vuecli3multi](https://github.com/shenshuai89/vue-cli3-temp/tree/vuecli3multi)