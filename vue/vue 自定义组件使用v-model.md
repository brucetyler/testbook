```
<input v-model="something">是我们常用的双向绑定方法，如果在自定义组件中如何使用v-model进行双向绑定呢？
```

```
首先我们必须要清除v-model绑定的原理如下：
```

```
其实v-model的语法糖是这样包装而成的：
<input
  :value="something"
  @:input="something = $event.target.value">
```

而一个组件上使用时则会简化成这样子：

```
<custom-input
  :value="something"
  @input="value =>{ something = value }">
</custom-input>
```

因此，对于一个带有 `v-model` 的组件（核心用法），它应该如下：

* 带有v-model的父组件通过绑定的value值（即v-model的绑定值）传给子组件，子组件通过 prop接收一个
  value;
* 子组件利用 $emit 触发 `input`事件，并传入新值value给父组件，即：

| `this.$emit('input', value);（注意：此时的input事件并非inpu标签的input事件，而是一个自定义事件（名字可以随便取），只是要和上面的对应）。如：this.$emit('a', value);上面就变成`@a="value =&gt;{ something = value }"，但是因为v-model是vue自身的语法糖，默认解析出来就是@input，所以我们一般都是用input命名） |
| :--- |


另外，由此可看出v-bind是单向绑定，v-model能实现双向绑定

[https://www.cnblogs.com/coffeelovetea/p/8326115.html](https://www.cnblogs.com/coffeelovetea/p/8326115.html)

