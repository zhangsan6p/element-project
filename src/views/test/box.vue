<template>
  <div class="home">
    <h3>div默认垂直排列</h3>
    <div class="box1">
      <div class="child1">1</div>
      <div class="child2">2</div>
      <div class="child3">3</div>
      <div class="child4">4</div>
      <div class="child5">5</div>
    </div>

    <h3>div变成盒子，将水平排列</h3>
    <div style="display: flex">
      <div class="child1">1</div>
      <div class="child2">2</div>
      <div class="child3">3</div>
      <div class="child4">4</div>
      <div class="child5">5</div>
    </div>

    <h3>主轴的row属性：水平从左往右排列</h3>
    <div class="box2" style="display: flex;flex-direction: row;">
      <div class="child1">1</div>
      <div class="child2">2</div>
      <div class="child3">3</div>
      <div class="child4">4</div>
      <div class="child5">5</div>
    </div>

    <h3>主轴的colum属性：垂直方向排列</h3>
    <div class="box2" style="display: flex;flex-direction: column;">
      <div class="child1">1</div>
      <div class="child2">2</div>
      <div class="child3">3</div>
      <div class="child4">4</div>
      <div class="child5">5</div>
    </div>

    <h3>主轴的column-reverse属性：垂直方向排列</h3>
    <div class="box2" style="display: flex;flex-direction: column-reverse;">
      <div class="child1">1</div>
      <div class="child2">2</div>
      <div class="child3">3</div>
      <div class="child4">4</div>
      <div class="child5">5</div>
    </div>

    <h3>主轴的对齐方式:左对齐</h3>
    <div class="box2" style="display: flex;justify-content: flex-start;">
      <div class="child1">1</div>
      <div class="child2">2</div>
      <div class="child3">3</div>
      <div class="child4">4</div>
      <div class="child5">5</div>
    </div>

    <h3>主轴的对齐方式:居中对齐</h3>
    <div class="box2" style="display: flex;justify-content: center;">
      <div class="child1">1</div>
      <div class="child2">2</div>
      <div class="child3">3</div>
      <div class="child4">4</div>
      <div class="child5">5</div>
    </div>

    <h3>主轴的对齐方式:右对齐</h3>
    <div class="box2" style="display: flex;justify-content: flex-end;">
      <div class="child1">1</div>
      <div class="child2">2</div>
      <div class="child3">3</div>
      <div class="child4">4</div>
      <div class="child5">5</div>
    </div>

    <h3>主轴的对齐方式:两端对齐</h3>
    <div class="box2" style="display: flex;justify-content: space-between;">
      <div class="child1">1</div>
      <div class="child2">2</div>
      <div class="child3">3</div>
      <div class="child4">4</div>
      <div class="child5">5</div>
    </div>

    <h3>主轴的对齐方式:space-around</h3>
    <div class="box2" style="display: flex;justify-content: space-around;">
      <div class="child1">1</div>
      <div class="child2">2</div>
      <div class="child3">3</div>
      <div class="child4">4</div>
      <div class="child5">5</div>
    </div>

    <h3>交叉轴的对齐方式:上对齐</h3>
    <div class="box2" style="display: flex;align-items: flex-start;">
      <div class="child1">1</div>
      <div class="child2">2</div>
      <div class="child3">3</div>
      <div class="child4">4</div>
      <div class="child5">5</div>
    </div>

    <h3>交叉轴的对齐方式:居中对齐</h3>
    <div class="box2" style="display: flex;align-items: center;">
      <div class="child1">1</div>
      <div class="child2">2</div>
      <div class="child3">3</div>
      <div class="child4">4</div>
      <div class="child5">5</div>
    </div>

    <h3>交叉轴的对齐方式:底部对齐</h3>
    <div class="box2" style="display: flex;align-items: flex-end;">
      <div class="child1">1</div>
      <div class="child2">2</div>
      <div class="child3">3</div>
      <div class="child4">4</div>
      <div class="child5">5</div>
    </div>

    <h3>子元素占比例分配</h3>
    <div class="box2" style="display: flex;">
      <div class="child1" style="flex-grow: 1;">1</div>
      <div class="child2" style="flex-grow: 1;">2</div>
      <div class="child3" style="flex-grow: 1;">3</div>
      <div class="child4" style="flex-grow: 1;">4</div>
      <div class="child5" style="flex-grow: 1;">5</div>
    </div>

  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {}
}
</script>

<style scoped>
.box1 {
  height: 300px;
  background-color: #d0d0d0;
}

.child1 {
  text-align: center;
  line-height: 50px;
  height: 50px;
  width: 50px;
  background-color: #ff00cc;
  color: #fff;
  border-radius: 50%;
}

.child2 {
  text-align: center;
  line-height: 50px;
  height: 50px;
  width: 50px;
  background-color: #cc6633;
  color: #fff;
  border-radius: 50%;
}

.child3 {
  text-align: center;
  line-height: 50px;
  height: 50px;
  width: 50px;
  background-color: #9966ff;
  color: #fff;
  border-radius: 50%;
}

.child4 {
  text-align: center;
  line-height: 50px;
  height: 50px;
  width: 50px;
  background-color: #3300ff;
  color: #fff;
  border-radius: 50%;
}

.child5 {
  text-align: center;
  line-height: 50px;
  height: 50px;
  width: 50px;
  background-color: #00dd00;
  color: #fff;
  border-radius: 50%;
}
</style>
