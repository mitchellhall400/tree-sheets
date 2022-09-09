<template>
  <table>
    <tr>
      <TreeCell :text="text" :table="table" />
    </tr>
  </table>
</template>

<script>
import TreeCell from "./components/TreeCell.vue";

export default {
  name: "App",
  components: {
    TreeCell,
  },
  data() {
    return {
      text: "Default template",
      table: [
        [
          { text: "1", table: [] },
          { text: "2", table: [] },
        ],
        [
          { text: "3", table: [] },
          { text: "4", table: [] },
        ],
      ],
    };
  },
  mounted() {
    const textContent = document.querySelectorAll(".textContent");
    for (let i = 0; i < textContent.length; i++) {
      textContent[i].addEventListener(
        "dblclick",
        (e) => {
          e.target.contentEditable = true;
        },
        false
      );
      textContent[i].addEventListener(
        "focusout",
        (e) => {
          e.target.contentEditable = false;
        },
        false
      );
    }
  },
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
body {
  background: #e6e6e6;
}
</style>
