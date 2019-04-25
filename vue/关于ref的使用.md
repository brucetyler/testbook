当你在一个dom元素中使用ref时，可以通过this.$refs来调用，但是分以下几种情况：

```
<el-form ref="noteForm"></form>
```

一般这样this.$refs获取的为单个ref对象：![](/assets/import2.png)用this.$refs.noteForm调用该元素



但是当该dom元素是循环渲染出来时，此时的this.$refs的单个ref为数组：

```
<div v-for="item in array">
<el-form ref="taskflowForm"></el-form>
</div>
```

![](/assets/import.png)

用this.$refs.taskflowForm\[0\]调用该元素

