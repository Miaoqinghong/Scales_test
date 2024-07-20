<template>
  <div class="container">
    <!-- 第一部分：文本框 -->
    <div class="text-section">
      <p>
        这里是文本框的内容，可以自动换行。在某些情况下，您是否会感到紧张或不按？安娜在被叫到全班同学面前讲
        话时会感到紧张
      </p>
    </div>

    <!-- 第二部分：图片展示区域 -->
    <div class="image-section">
      <div v-for="(image, index) in images" :key="index" :class="['image-wrapper', `size-${images.length}`]">
        <img :src="image" alt="pic1" />
      </div>
    </div>

    <!-- 第三部分：四个按钮 -->
    <div class="button-section">
      <button
        v-for="(button, index) in buttons"
        :key="index"
        :class="{'selected': selectedButton === index, 'unselected': selectedButton !== index}"
        @click="selectButton(index)"
      >
        {{ button.text }}
      </button>
    </div>

    <!-- 第四部分：分页按钮 -->
<!-- 第四部分：分页按钮 -->
  <div class="pagination-section">
    <img src="./image_demo/button_pre.png" alt="上一页" @click="prevPage" class="pagination-button" />
    <img src="./image_demo/button_next.png" alt="下一页" @click="nextPage" class="pagination-button" />
  </div>
  </div>
</template>

<script>
import pic1 from "./image_demo/001.png"

export default {
  data() {
    return {
      images: [
        pic1,
        pic1,
        pic1,
      

        //'path/to/image2.jpg',
        //'path/to/image3.jpg',
        //'path/to/image4.jpg'
      ],
      buttons: [
        {text:'按钮1'},
        {text:'按钮1'},
        {text:'按钮1'},
        {text:'按钮1'}
      ],
      selectedButton:null
    };
  },
  methods: {
    selectButton(index){
      this.selectedButton = index;
    },
    prevPage() {
      // 处理上一页逻辑
    },
    nextPage() {
      // 处理下一页逻辑
    }
  }
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  height: 100vh;
  padding: 20px;
  box-sizing: border-box;
}

.text-section {
  width: 100%;
  max-width: 1380px;
  text-align: left;
  word-wrap: break-word;
  /*border: 1px solid #ccc;*/
  padding: 10px;
  margin-bottom: 20px;
  font-family:sans-serif;
  font-size:larger;
  margin-top: 50px;
  color: black;
}

.image-section {
  display: flex;
  width: 100%;
  max-width: 1380px;
  margin-bottom: 20px;
  margin-top: 0;
  align-items: center;
  justify-content: space-around;
  margin-top: 50px;
  margin-bottom: 30px;
}

.image-wrapper {
  /* display: flex;
  justify-content: center;
  align-items: center; */
  width: 300px;
  height: 300px;
}
.image-wrapper.size-1{
  width: 450px;
  height: 450px;
}
.image-wrapper.size-2{
  width: 400px;
  height: 400px;
}
.image-wrapper.size-3{
  width: 380px;
  height: 380px;
}
.image-wrapper.size-4{
  width:320px;
  height: 320px;
}

.image-wrapper img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.button-section {
  display: flex;
  justify-content: space-between;
  width: 100%;
  max-width: 1000px;
  margin-bottom: 20px;
  margin-top: 50px;
}

.button-section button {
  width: 150px;
  height: 55px;
  border-radius: 50px;
  border: 2px solid #4d90fe; /* 默认边框颜色为蓝色 */
  background-color: #ffffff; /* 默认背景色为白色 */
  color: #4d90fe; /* 文字颜色为蓝色 */
  font-size: 16px;
  cursor: pointer;
  outline: none;
  display: flex;
  justify-content: center;
  align-items: center;
}

.button-section button.selected {
  background-color: #4d90fe; /* 选中时背景色为蓝色 */
  color: #ffffff; /* 选中时文字颜色为白色 */
  border: none; /* 选中时移除边框 */
}

.button-section button.unselected {
  background-color: #ffffff; /* 未选中时背景色为白色 */
  color: #4d90fe; /* 未选中时文字颜色为蓝色 */
  border: 2px solid #4d90fe; /* 未选中时边框为蓝色 */
}

.pagination-section {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  width: 1200;
  padding: 10px;
  position: fixed;
  bottom: 150px;
  right: 270px;
}

.pagination-button {
  margin-left: 40px;
  width: 40px; /* 根据图片实际大小调整 */
  height: 40px; /* 根据图片实际大小调整 */
  cursor: pointer;
}

.pagination-button:first-child {
  margin-left: 0;
}

@media (max-width: 768px) {
  .text-section, .image-section, .button-section {
    width: 100%;
  }

  .button-section button {
    margin: 5px;
  }

  .pagination-section {
    position: relative;
    justify-content: center;
    bottom: auto;
    right: auto;
  }
}
</style>