<template>
  <td>
    <div class="textContent">{{cellContent}}</div>
    <table v-if="table != 0">
      <tbody>
        <tr v-for="(row, i) in table" :key="i">
          <TreeCell v-for="(data, j) in row" :key="j" v-bind="data" />
        </tr>
      </tbody>
    </table>
  </td>
</template>

<script>
import TreeCell from "./TreeCell.vue";

export default {
  name: "TreeCell",
  components: {
    TreeCell,
  },
  props: {
    text: {
      type: String,
      required: true,
    },
    table: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  data() {
    return {
      cellContent: this.text,
    };
  },
};
</script>

<style>
table {
  border-spacing: 0;
  margin: 10px;
}
td {
  border: solid #a0a0a0 1px;
  padding: 4px;
  background: #fff;
}
tr:first-child > td:first-child {
  border-top-left-radius: 4px;
}
tr:first-child > td:last-child {
  border-top-right-radius: 4px;
}
tr:last-child > td:first-child {
  border-bottom-left-radius: 4px;
}
tr:last-child > td:last-child {
  border-bottom-right-radius: 4px;
}
</style>