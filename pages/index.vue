<template>
  <section class="container">
    <graph-content />
  </section>
</template>

<script>
import GraphContent from '~/components/GraphContent'

export default {
  components: {
    GraphContent
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
