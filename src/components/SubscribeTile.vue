<template>
  <div class="subscribe-tile bg-white rounded-[12px] px-[16px] py-[24px]">
    <div class="tile-title-block flex flex-row mb-[8px]">
      <div class="title-time flex flex-col">
        <div class="time text-[#999999] text-[13px] leading-[16px]">{{item.time}}</div>
        <div class="title font-500 text-[20px] leading-[28px]">{{item.title}}</div>
      </div>
      <div class="title-image flex ml-auto">
        <img :src="`/images/${item.image}.png`" :alt="item.title" class="w-[40px] h-[40px]">
      </div>
    </div>
    <div class="tile-description text-[#666666] text-[14px] leading-[20px] mb-[16px]">{{item.description}}</div>
    <div class="tile-list-content-block mb-[24px]">
      <ul>
        <li v-for="(cItem, index) in item.content" :key="item.id + index"
            class="text-[14px] leading-[20px]"
        >{{cItem}}</li>
      </ul>
    </div>
    <div class="tile-total-block">
      <subscribe-tile-btn :text="item.count" />
    </div>
  </div>
</template>

<script setup>

import SubscribeTileBtn from "@/components/SubscribeTileBtn.vue";

defineProps({
  item: {
    type: Object
  }
})


</script>

<style scoped lang="scss">
.subscribe-tile {
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.08);
}
li {
  display: flex;
  margin-bottom: 8px;
  &::before {
    content: url("@/assets/check.png");
    display: flex;
    margin-right: 8px;
    margin-top: auto;
    margin-bottom: auto;
  }
}
</style>