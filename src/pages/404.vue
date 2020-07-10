<template>
  <Layout>
    <div class="error">
      <h1 class="error__name">404</h1>
      <h2 class="error__small-header">nothing to see here</h2>
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: "404",
  },
};
</script>

<style scoped>
.error {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100%;
}

.error__name,
.error__small-header {
  margin: 0;
  color: #ffffff;
  font-weight: lighter;
  text-align: center;
}
</style>
