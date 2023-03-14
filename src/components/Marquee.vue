<script setup lang="ts">
import { onMounted } from 'vue'

const props = defineProps<{
    msg: string
    width: Number,
    height: Number
}>()

const width = {
    type: Number,
    default() {
        return props.width??400
    }
};
const height = {
    type: Number,
    default() {
        return props.height??100
    }
}

onMounted(()=>{
    // 在mounted阶段，才可以获取真实DOM节点
    const showArea: any = document.querySelector('.show-area')
    //从左到右滚动，首先把滚动条置到元素的最右边
    showArea.scrollLeft = showArea.scrollWidth
    function f() {
      //如果滚动条到了元素的最左边，那么把它再初始化到最右边
      if (showArea.scrollLeft < 3) {
        showArea.scrollLeft = showArea.scrollWidth
      } else {
        //每次滚动条向左移动2，改变speed可以调整滚动速度
        const speed = 2
        showArea.scrollLeft -= speed
      }
      //使用requestAnimationFrame，优化滚动效果
      //requestAnimationFrame使得滚动和机器帧率同步
      requestAnimationFrame(f)
    }
    requestAnimationFrame(f)
})
</script>

<template>
    <div class="show-area" :style="{ width: `${width}px`, height: `${height}px` }">
        <div class="scroll-area">
            <!-- 设置margin，使内容 有从无到有的出现效果 -->
            <div class="slot-container" :style="{ margin: `0 ${width}px` }">
                <slot>1111111111111</slot>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.show-area {
  // height: 50px;
  display: inline-block;
  white-space: nowrap;
  overflow: hidden;
  .scroll-area {
    display: inline-block;
    .slot-container {
      display: inline-block;
    }
  }
}
</style>