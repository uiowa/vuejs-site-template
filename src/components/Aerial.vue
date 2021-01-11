<template>
<div class="aerial aerial__grid">
	<div class="aerial__image">
    <img class="aerial__img" :src="aerial_image" alt="Alt Text" loading="lazy">
	</div>
  <div class="aerial__container">
    <div class="aerial__content aerial__content-grid">
      <Highlight
        :highlight_title="grid_title_1"
        :highlight_sub="grid_sub_1"
      />

      <Highlight
        :highlight_title="grid_title_2"
        :highlight_sub="grid_sub_2"
      />

      <Highlight
        :highlight_title="grid_title_3"
        :highlight_sub="grid_sub_3"
      />

      <Headline v-if="typeof aerial_title !== 'undefined'"
        headline_level="h2"
        headline_class="headline headline--uppercase"
        :headline="aerial_title"
      />

      <Highlight
        :highlight_title="grid_title_4"
        :highlight_sub="grid_sub_4"
      />
    </div>
	</div>
</div>
</template>

<script>
import Highlight from './Highlight.vue';
import Headline from './Headline.vue';

export default {
  name: 'Aerial',

  components: {
    Highlight,
    Headline
  },

  props: {
    aerial_title: {
      type: String
    },
    aerial_image: {
      type: String
    },
    grid_title_1: {
      type: String
    },
    grid_sub_1: {
      type: String
    },
    grid_title_2: {
      type: String
    },
    grid_sub_2: {
      type: String
    },
    grid_title_3: {
      type: String
    },
    grid_sub_3: {
      type: String
    },
    grid_title_4: {
      type: String
    },
    grid_sub_4: {
      type: String
    }
  }
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/viewbook/aerial/aerial.scss';
</style>
