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
    <SubscribesNav />
    <section class="main-content-block
             w-full bg-[#F5F5F8]
             px-[16px] lg:px-[24px] py-[32px] lg:py-[48px]
             lg:rounded-[16px]">
      <h2 class="main-content-title
      w-full flex font-500 text-[24px] leading-[32px] letter-[-1%] pb-[16px]
      lg:justify-center lg:pb-[24px]">
        Выберите рассылки, которые подходят именно вам</h2>
      <EmailForm />
      <subscribe-all-btn class="mb-[24px]" />
      <div class="subs-list
                  grid lg:grid-cols-2 gap-[24px]">
        <subscribe-tile
            v-for="item in subscribesItems" :key="item.id" :item="item"
        />
      </div>

    </section>
    <BottomBlock />

  </div>
</template>

<script setup>
import BreadCrumbs from "@/components/BreadCrumbs.vue";
import SubscribeAllBtn from "@/components/SubscribeAllBtn.vue";
import SubscribeTile from "@/components/SubscribeTile.vue";
import SubscribesNav from "@/components/SubscribesNav.vue";
import EmailForm from "@/components/EmailForm.vue";
import BottomBlock from "@/components/BottomBlock.vue";

const breadcrumbsItems = [
  {text: 'Главная', link: '/'},
  {text: 'Рассылки', link: '/'},
  {text: 'Хлебные крошки', link: '/'},
]

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




</script>

<style scoped lang="scss">
</style>