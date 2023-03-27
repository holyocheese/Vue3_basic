<template>
  <div>
    <div class="history"><p class="historyText">历史记录列表</p></div>
    <div class="content">
      <div class="white-box">Chat</div>
    </div>
  </div>
</template>

<style>
.history {
  float: left;
  width: 20%;
  height: 100vh;
  background-color: #363636;
}
.historyText{
  margin-top: 20px;
  color: #e6e6e6;
  text-align: center;
}
.content {
  float: left;
  width: 80%;
  height: 100vh;
}

.white-box {
  min-width: 1024px;
  height: calc(100vh - 20px); /* 留出的20px是历史记录列表的高度 */
  background-color: #fff;
}
</style>