<template>
  <div id="cell-changed">
    <mt-input
      :id="data.column.field"
      v-model="data[data.column.field]"
      :disabled="isDisabled"
    ></mt-input>
  </div>
</template>
<script>
export default {
  data() {
    return { data: {}, isDisabled: false };
  },
  mounted() {
    if (
      this.data.column.field === "scheduleArea" ||
      this.data.column.field === "associatedNumber" ||
      this.data.column.field === "buyerOrgName" ||
      this.data.column.field === "remark" ||
      this.data.column.field === "saleOrder" ||
      this.data.column.field === "saleOrderRowCode" ||
      this.data.column.field === "processName" ||
      this.data.column.field === "productCode" ||
      this.data.column.field === "buyerOrder" ||
      this.data.column.field === "buyerOrderRowCode" ||
      this.data.column.field === "projectTextBatch" ||
      this.data.column.field === "warehouseKeeper"
    ) {
      //计划区域 关联工单号
      this.setDisabled();
    }
  },
  methods: {
    setDisabled() {
      if (this.data.isEntry === "1") {
        this.isDisabled = true;
      }
      if (this.data.isEntry === "2") {
        this.isDisabled = false;
      }
    },
  },
};
</script>
