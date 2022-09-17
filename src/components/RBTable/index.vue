<template>
  <div class="main">
    <el-table
      :data="tableData"
      :height="height"
      :stripe="stripe"
      :border="border"
      :size="size"
      :fit="fit"
      :showHeader="showHeader"
      :highlightCurrentRow="highlightCurrentRow"
      :emptyText="emptyText"
    >
      <slot name="behind" />
      <el-table-column
        v-for="item in columns"
        :key="item.prop"
        :prop="item.prop"
        :label="item.label"
        :width="item.width ? item.width : ''"
        :align="item.align ? item.width : 'center'"
      />
      <slot name="before" />
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
      default: true
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
  padding: auto;
  border: auto;
}
</style>
