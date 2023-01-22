<template>
  <footer class="footer">
    <h4>
      {{
        `${new Date().getFullYear() - 1} ${new Date().getFullYear()} 
        Made By Vaibhav`
      }}
    </h4>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style scoped>
.footer {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  background: #2c3333;
  color: #fff;
  text-align: center;
  padding: 10px;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}
</style>


