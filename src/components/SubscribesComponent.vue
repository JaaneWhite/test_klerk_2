<template>
  <div class="subscribes-block
              mx-auto w-full max-w-screen-lg
              pt-[24px] lg:pt-[48px]
">
    <div class="logo-block w-full pb-[28px] lg:pb-[24px]">
      <img
          src="@/assets/klerk.png"
          class="mx-auto"
          alt="logo"
      />
    </div>
    <div class="breadcrumbs-block w-full flex flex-row justify-center">
      <bread-crumbs :items="breadcrumbsItems" />
    </div>
    <div class="title-block w-full flex flex-row justify-center">
      <h1 class="title-block-h font-500
      mt-[8px] lg:mt-[24px] mb-[24px]
      text-[32px] lg:text-[56px]
      leading-[42px] lg:leading-[72px]">Подписки «Клерка»</h1>
    </div>
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
    <div class="main-content-block w-full bg-[#F5F5F8] px-[16px] py-[32px]" >
      <h2 class="main-content-title
      w-full font-500 text-[24px] leading-[32px] letter-[-1%] pb-[16px]">Выберите рассылки, которые подходят именно вам</h2>
      <form class="email-form w-full h-[56px] relative ">
        <input type="email"
               placeholder="Электронная почта"
               class="w-full h-[56px] rounded-r-[100px] rounded-l-[4px] p-[16px]
               placeholder:text-[#666666] placeholder:text-[16px]
" />
        <button class="email-btn h-[56px] w-[56px] rounded-full bg-[#316FEE] text-white absolute top-0 right-0">
          <img
              src="@/assets/arrow.png"
              class="mx-auto"
              alt="logo"
          />
        </button>
      </form>
      <div class="subscribe-all-block w-full flex flex-row">
        <button class="switch-btn small">
          <span class="round rounded-full "></span>
        </button>
      </div>
    </div>

  </div>
</template>

<script setup>
import BreadCrumbs from "@/components/BreadCrumbs.vue";
import {reactive, ref} from "vue";

const breadcrumbsItems = [
  {text: 'Главная', link: '/'},
  {text: 'Рассылки', link: '/'},
  {text: 'Хлебные крошки', link: '/'},
]

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
    }
    &.active {
      color: #5A8CF1;
      border-bottom: 2px solid #5A8CF1;
    }
  }
  

}
</style>