<template>
  <div class="subscribe-all-block w-full flex flex-row">
    <button
        class="switch-btn small"
        :class="switchedOn ? 'switched-on' : ''"
        @click="switchedOn = !switchedOn"
    >
      <div class="round"></div>
    </button>
    <span class="btn-text text[14px] leading-[20px]">{{text}}</span>
  </div>
</template>

<script setup>
import {ref} from "vue";

let switchedOn = ref(false)

defineProps({
  text: {
    type: String
  }
})

</script>

<style scoped lang="scss">
.switch-btn {
  width: 48px;
  height: 24px;
  background-color: #EEEEEE;
  border-radius: 16px;
  padding: 0;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  transition: all 2ms;
  margin-top: auto;
  margin-bottom: auto;
  margin-right: 16px;

  .round{
    width: 21px;
    height: 21px;
    background-color: white;
    border-radius: 50%;
    margin-left: 1.5px;
    margin-right: 1.5px;

  }
  &.switched-on {
    background-color: #316FEE;
    justify-content: flex-end;
  }
}
.btn-text {

}
</style>