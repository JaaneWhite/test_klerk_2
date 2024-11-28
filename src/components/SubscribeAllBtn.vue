<template>
  <div class="subscribe-all-block w-full flex flex-row">
    <button
        class="switch-btn small"
        :class="switchedOn ? 'switched-on' : ''"
        @click="switchedOn = !switchedOn"
    >
      <div class="round"></div>
    </button>
    <span class="btn-text text[14px] leading-[20px]">Подписаться на все рассылки</span>
  </div>
</template>

<script setup>
import {ref} from "vue";

let switchedOn = ref(false)
</script>

<style scoped lang="scss">
.switch-btn {
  width: 32px;
  height: 16px;
  background-color: #DCDCDC;
  border-radius: 16px;
  padding: 0;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  transition: all 2ms;
  margin-top: auto;
  margin-bottom: auto;
  margin-right: 8px;


  .round{
    width: 14px;
    height: 14px;
    background-color: white;
    border-radius: 50%;
    margin: 1px;
  }
  &.switched-on {
    background-color: #316FEE;
    justify-content: flex-end;
  }
}
.btn-text {

}
</style>