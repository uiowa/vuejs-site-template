<template>
<div class="stat__wrapper bg--black">
  <template v-for="(stat, index) in stats" :key="index">
    <stat
      :headline="stat.headline"
      :headline_prefix="stat.headline_prefix"
      :headline_suffix="stat.headline_suffix"
      :stat_description="stat.stat_description"
      :stat_content="stat.stat_content"
      :stat_vertical="stat.stat_vertical"
    />
  </template>
</div>
</template>

<script>

import Stat from './Stat.vue';
export default {
    name: "statWrapper",

    props: {
      stats: {
        type: Array
      },
    },
    components: {
      Stat
    }
}
</script>

<style scoped>

</style>