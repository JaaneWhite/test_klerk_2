<template>
  <div class="breadcrumbs">
    <span
        v-for="(item, index) in items" :key="index"
        class="breadcrumb-item"
    >
      <a
          :href="item.link"
          class="breadcrumb-link"
      >{{ item.text }}</a>
    </span>
  </div>
</template>

<script setup>
defineProps({
  items: {
    type: Array
  }
})

</script>

<style scoped lang="scss">
@media (min-width: 0) {
  .breadcrumbs {
    .breadcrumb-item {

      &:not(:last-child)::after{
        content: "→";
        margin-left: 8px;
        margin-right: 8px;
        font-size: 13px;
        color: #999999;
      }

      .breadcrumb-link {
        font-size: 13px;
        line-height: 16px;
        color: #999999;
        border-bottom: 1px solid #E6EDFF;
      }

    }

  }
}
</style>