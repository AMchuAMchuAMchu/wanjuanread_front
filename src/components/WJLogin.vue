<template>
  <div>
    <!--背景大盒子-->
    <div class="box_bg">
      <!--装载asuna_bg_index.jpg图片的盒子-->
      <div class="bg_index_box01">
        <img id="bg_index" src="../assets/img_index/asuna_bg_index.jpg" alt="图片找不到..">
      </div>
      <h1>刀剑神域</h1>
      <h1>结城明日奈</h1>
      <!--装载登录表单和背景图片的盒子-->
      <div class="box01">
        <!--装载登录表单的盒子-->
        <div class="box_login">
          <form action="" method="post">
            <div class="l1">
              用户名:<input name="username" type="text">
            </div>
            <div class="l2">
              密&emsp;码:<input name="password" type="password">
            </div>
            <div class="l3">
              <button type="submit">提交</button>
            </div>
          </form>
        </div>
        <!--背景图片-->
        <img id="bg_login" src="../assets/img_index/asuna1001.jpg" alt="果咩纳塞~~图片找不到...">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "WJLogin"
}
</script>

<style scoped>
/**
    清除浏览器默认内外边距样式设置
 */
* {
  padding: 0;
  margin: 0;
}

/**
    大的背景盒子样式
 */
.box_bg {
  width: 100%;
  height: 100%;
}

/**
    背景图片(asuna_bg_index.jpg)样式,背景图片平铺水平铺满
 */
#bg_index {
  width: 100%;
}

/**
    背景图片用一个div盒子包起来,方便后面实现绝对定位和z-index置底层的操作,最后作为index的大背景图片
 */
.bg_index_box01 {
  position: absolute;
  width: 100%;
  z-index: -1;
  opacity: 0.4;
}

/**
    装第二张亚丝娜背景图片(asuna1001.jpg)的盒子样式设置
 */
.box01 {
  position: relative;
  width: 400px;
  height: 539px;
  margin: 10px auto;
  background-color: aqua;
  opacity: 0.8;
  text-align: center;
}

/**
    第二张亚丝娜图片的样式设置
 */
#bg_login {
  width: 100%;
}

/**
    一级标题内容居中
 */
h1 {
  text-align: center;
}

/**
    装载登录form表单的盒子样式设置
 */
.box_login {
  position: absolute;
  width: 300px;
  height: 200px;
  margin-top: 117px;
  /* 这里的水平居中的话只能计算了:大盒子的一半减去小盒子的一半
   */
  margin-left: 50px;
  background-color: red;
}

.l1 {
  margin-top: 25px;
}

.l2 {
  margin-top: 25px;
}
.l3{
  margin-top: 19px;
  margin-left: 188px;
}
</style>
