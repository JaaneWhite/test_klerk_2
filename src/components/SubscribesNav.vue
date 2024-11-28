<template>
  <nav class="subscribes-nav w-full">
    <ul class="subscribes-nav-list w-full flex flex-row justify-center">
      <li v-for="item in navItems" :key="item.id"
          :class="{active: navActive.id === item.id}"
          @click="selectNavItem(item)"
          class="nav-item"
      >
        {{item.title}}
      </li>
    </ul>
  </nav>
</template>

<script setup>
import {reactive, ref} from "vue";

const navItems = reactive([
  {id: 'subs', title: 'Рассылки', block: '' },
  {id: 'nets', title: 'Соцсети', block: '' },
  {id: 'mess', title: 'Мессенджеры', block: '' },
])
let navActive = ref({id: 'subs', title: 'Рассылки', block: '' })

function selectNavItem(navItem) {
  navActive.value = navItem
}

</script>

<style scoped lang="scss">
@media (min-width: 0) {
  .nav-item {
    color: #666666;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    border-bottom: 2px solid transparent;
    padding-bottom: 16px;
    padding-left: 8px;
    padding-right: 8px;
    &:hover {
      cursor: pointer;
      color: #5A8CF1;
    }
    &.active {
      color: #5A8CF1;
      border-bottom: 2px solid #5A8CF1;
    }
  }


}
</style>