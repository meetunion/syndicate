<template>
  <div class="header">
    <img :src="coverImageURL" alt="" />
    <h1>{{ title }}</h1>
    <div>{{ description }}</div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    title: String,
    description: String,
    coverImageURL: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss"></style>
