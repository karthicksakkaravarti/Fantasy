<template>
   <router-view/>
</template>

<script>
export default {
  name: "App",
  watch: {
    $route(to) {
      document.title = to.meta.title || "Fantacy";
    },
  },
  data: () => ({
    //
  }),
};
</script>
