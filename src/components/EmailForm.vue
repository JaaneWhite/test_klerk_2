<template>
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
        bg-[#316FEE] text-white absolute top-0 right-0 hover:bg-[#5A8CF1]"
    >
      <img
          src="@/assets/arrow.png"
          class="mx-auto lg:hidden"
          alt="logo"
      />
      <span class="sm:hidden lg:flex text-[16px] text-white leading-[24px] m-auto">Подписаться</span>
    </button>
  </form>
</template>

<script setup>
</script>

<style scoped>

</style>