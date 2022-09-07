<template>
  <div class="container">
    <CardComponent/>
  </div>
</template>

<script>
import CardComponent from './CardComponent.vue';
export default {
    name: "MainContent",
    components: { CardComponent },
    props: {},
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
