# Example

将你自己的组件或内容放入 `EdgeOpacity` 组件中即可！  
然后你就看到边缘的透明度渐变了！

# How to use

```html
<template>
  <EdgeOpacity :range="range" :edge-opacity="edgeOpacity">
    <div class="dv">
      你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容你自己的组件或内容
    </div>
  </EdgeOpacity>
</template>

<script>
  import EdgeOpacity from "edge-opacity/src/EdgeOpacity.vue";
  export default {
    components: {
      EdgeOpacity,
    },
    data: {
      range: "10% 5%", // 透明渐变范围，可以有1、2、3、4个值，单位为'%'，语法参考https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding#%E8%AF%AD%E6%B3%95
      edgeOpacity: 0, // 边缘透明度，范围0~1，值为0时，边缘纯透明，值为1时，边缘纯不透明
    },
  };
</script>

<style>
  .dv {
    width: 400px;
    height: 400px;
    background-color: goldenrod;
  }
</style>
```