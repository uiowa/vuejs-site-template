<template>
  <div :class="getStatClasses()">
    <div>
      <Headline
        v-if="headline"
        headline_level="h2"
        class="stat__title"
        :headline="headline"
        :headline_prefix="headline_prefix"
        :headline_suffix="headline_suffix"
      />
    </div>
    <p v-html="stat_description" class="stat__description"></p>
    <p v-html="stat_content" class="stat__content"></p>
  </div>
</template>

<script>
import Headline from './Headline.vue';

export default {
    name: 'Stat',

    props: {
      headline: {
        type: String
      },
      headline_prefix: {
        type: String
      },
      headline_suffix: {
        type: String
      },
      image: {
        type: String
      },
      link_url: {
        type: String
      },
      stat_description: {
        type: String
      },
      stat_content: {
        type: String
      },
      stat_vertical: {
        type: Boolean
      }
    },

    components: {
        Headline,
    },

  methods: {
    /*
        This method builds the classes for the stat.
        It composes a string out of the classes passed to the component, and then if 'stat_vertical' is true, adds a class to make the stat vertical.
    */
    getStatClasses() {
      let classes = 'stat__grid stat stat--horizontal';
      if (this.$props.stat_vertical) {
        classes += ' element--flex-center';
      }
      else {
        classes += ' element--flex-left';
      }
      return classes;
    }
  }
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/stat/stat.scss';
</style>
