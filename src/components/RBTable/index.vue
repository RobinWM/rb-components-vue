<template>
  <div class="main">
    <el-table
      :data="tableData"
      style="width: 100%"
      :height="height"
      :stripe="stripe"
      :border="border"
      :size="size"
      :fit="fit"
      :showHeader="showHeader"
      :highlightCurrentRow="highlightCurrentRow"
      :emptyText="emptyText"
    >
      <el-table-column
        v-for="item in columns"
        :key="item.prop"
        :prop="item.prop"
        :label="item.label"
        :width="item.width ? item.width : 120"
      />
    </el-table>
  </div>
</template>

<script>
export default {
  name: "RBTable",
  props: {
    columns: {
      type: Array,
      default: () => []
    },
    tableData: {
      type: Array,
      default: () => []
    },
    height: String,
    stripe: {
      type: Boolean,
      default: false
    },
    border: {
      type: Boolean,
      default: false
    },
    size: String,
    fit: {
      type: Boolean,
      default: true
    },
    showHeader: {
      type: Boolean,
      default: true
    },
    highlightCurrentRow: {
      type: Boolean,
      default: false
    },
    emptyText: String
  },
  data() {
    return {};
  }
};
</script>

<style scoped>
.main {
  width: 1000px;
  border: 1px solid #999;
}
</style>
