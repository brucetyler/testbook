对于vue中循环或递归多个checkbox并绑定其对应选中状态时

此时 v-model 绑定的数据也是动态生成的

我们可以定义的 data 的 form 里面是空对象，用来保存对应的绑定状态

```
export default {
  data() {
    return {
      form: {}
    }
  },
}
```

模板的结构如下：

```
<div v-for="item in data">
<el-checkbox v-model="form[item.id]">
    </el-checkbox>
</div>
```



