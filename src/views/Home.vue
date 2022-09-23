<template>
  <h1>首页</h1>
  <h2>{{ a }}</h2>
  <h2>{{ b }}</h2>
  <h2>{{ c }}</h2>
  <button @click="asd">改变值</button>
</template>

<script >
import { defineComponent, ref, reactive } from "vue";
// setup(类似于data，包含methods,不管是方法还是定义的单个数据，都要return出去) 用法 setup(){ a:1 return:{a} }
//ref 定义动态数据，只有被ref属性包装以后才可以实现动态改变, let a = ref(1)  const changea()=>{ a.value ++ }
//reactive 定义动态对象或者数组, let obj = reactive({a:2})
// torefs()  在对象使用 ... 在return中时 使用它来进行包装
export default defineComponent({
  name: "Home",
  setup() {
    let a = ref(1);
    let b = reactive({
      name: "don",
    });
    let c = reactive([{ age: 10 }]);
    const asd = () => {
      a.value++;
      b.name += "--";
      c[0].age++;
      c.push({ log: "旺旺" });
    };
    return {
      a,
      b,
      c,
      asd,
    };
  },
});
</script>
