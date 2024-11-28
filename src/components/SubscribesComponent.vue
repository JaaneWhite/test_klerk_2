<template>
  <div class="subscribes-block
              mx-auto w-full max-w-[1024px]
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
    <section class="main-content-block
             w-full bg-[#F5F5F8]
             px-[16px] lg:px-[24px] py-[32px] lg:py-[48px]
             lg:rounded-[16px]">
      <h2 class="main-content-title
      w-full flex font-500 text-[24px] leading-[32px] letter-[-1%] pb-[16px]
      lg:justify-center lg:pb-[24px]">
        Выберите рассылки, которые подходят именно вам</h2>
      <form class="email-form w-full h-[56px] relative mb-[16px] lg:mb-[18px]">
        <input type="email"
               placeholder="Электронная почта"
               class="w-full h-[56px] rounded-r-[100px] rounded-l-[4px] p-[16px]
               lg:rounded-l-[8px]
               placeholder:text-[#666666] placeholder:text-[16px]" />
        <button class="email-btn
        h-[56px] w-[56px] rounded-full
        lg:w-[163px] rounded-[100px]
        lg:flex justify-center justify-items-center
        bg-[#316FEE] text-white absolute top-0 right-0">
          <img
              src="@/assets/arrow.png"
              class="mx-auto lg:hidden"
              alt="logo"
          />
          <span class="sm:hidden lg:flex text-[16px] text-white leading-[24px] m-auto">Подписаться</span>
        </button>
      </form>
      <subscribe-all-btn class="mb-[24px]" />
      <div class="subs-list
                  grid lg:grid-cols-2 gap-[24px]
">
        <subscribe-tile
            v-for="item in subscribesItems" :key="item.id" :item="item"
        />
      </div>

    </section>
    <div class="bottom w-full flex justify-center pt-[48px] pb-[48px]">
      <img src="/images/bottom_img.png">
    </div>

  </div>
</template>

<script setup>
import BreadCrumbs from "@/components/BreadCrumbs.vue";
import {reactive, ref} from "vue";
import SubscribeAllBtn from "@/components/SubscribeAllBtn.vue";
import SubscribeTile from "@/components/SubscribeTile.vue";

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

const subscribesItems = [{
    id: 1,
    time: 'Перед рассветом',
    title: 'Утренний бухгалтер',
    description: 'Самые важные новости и события за день. Кратко, по делу, структурировано.',
    content: [
        'Новости для бухгалтеров, ИП и директора',
        'Подборка статей за день'
    ],
    count: 'Уже получает 59 342 человек',
    image: 'skrepka'
  },
  {
    id: 2,
    time: 'После заката',
    title: 'Ночной бухгалтер',
    description: 'Самая краткая газета о налогах и бухучете в мире — современная рассылка для вечернего чтения.',
    content: [
      'Новости для бухгалтеров, ИП и директора',
      'Подборка статей за день'
    ],
    count: 'Уже получает 59 342 человек',
    image: 'skrepka_dark'
  },
  {
    id: 3,
    time: 'Раз в две недели',
    title: 'Ножницы скидок',
    description: 'Подборка самых выгодных и полезных спецпредложений от надежных компаний.',
    content: [
        'Акции и скидки от лидеров рынка',
        'Те, кто подписался – экономят много денег 🤑'
    ],
    count: 'Уже получает 59 342 человек',
    image: 'scissors'
  },
  {
    id: 4,
    time: 'По мере появления анонсов',
    title: 'Чемодан вебинаров',
    description: 'Подборка с анонсами бесплатных вебинаров на самые топовые темы при участии экспертов.',
    content: [
        'Никогда не пришлем платные вебинары',
        'Подборка топовых тем для вебинаров'
    ],
    count: 'Уже получает  92 082 человек',
    image: 'vebinar'
  }
]

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