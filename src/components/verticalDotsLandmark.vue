<template>
<div class="v-dots-scroll-spacer">
  <div class="v-dots-scroll-target" :id="landmark_title.toLocaleLowerCase().replaceAll(/[\W_]+/g, '-')"></div>
</div>
<slot></slot>
</template>

<script>

export default {
  name: "verticalDotsLandmark",
  props: {
    landmark_title: {
      type: String
    },
  }
}
</script>