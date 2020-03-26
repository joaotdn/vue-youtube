<template>
  <div>
    <input type="search" @input="onInput" />
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  methods: {
    onInput(e) {
      this.$emit("termChange", e.target.value);
    }
  }
};
</script>

<style lang="sass"></style>
