
<template>
  <h2>Article Component</h2>
  <h2>{{title}} - Likes {{likes}} - Is Published {{ isPublished ? 'Yes' : 'No' }}</h2>

  <h2  v-bind="$attrs" >Passing - Non Prop Attributes </h2>
</template>

<script>
export default {
  name: "ArticleComponent",
  props: {
    title: {
      type: String,
      required: true,
      default: 'Article default value'
    },
    likes: Number,
    isPublished: Boolean,
  },
  inheritAttrs: false,
};
</script>

<style scoped></style>
