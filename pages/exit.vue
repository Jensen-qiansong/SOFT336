<template>
  <div class></div>
</template>
<script>
export default {
  layout: "blank",
  middleware: async ctx => {
    //middleware中间件
    let { status, data } = await ctx.$axios.get("/users/exit");
    if (status === 200 && data && data.code === 0) {
      location.href = "/";
    }
  }
};
</script>
<style >

</style>