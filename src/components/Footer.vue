<template>
  <footer>
    <p>Copyright ⓒ Sergei Sevriugin {{year}}</p>
  </footer>
</template>

<script>
export default {
  name: "Footer",
  data: function() {
    return {
      year: new Date().getFullYear()
    };
  }
};
</script>

