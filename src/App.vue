<template>
  <div>
    <h2>My First Azure Static Web App</h2>
    <div>{{ message }}</div>
  </div>
</template>

<script>

export default {
  name: "App",
  data() {
    return {
      message: ""
    };
  },
  async mounted() {
    const { text } = await(await fetch("/api/message")).json();
    this.message = text;
  }
};
</script>
