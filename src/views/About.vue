<template>
  <div class="about">
    <h1>This is an about page</h1>
    <e-charts :options="option" />
    <n-alert title="alert" type="success"></n-alert>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import ECharts from "@/components/ECharts.vue";
export default defineComponent({
  name: "Abount",

  components: { ECharts },
  data() {
    return {
      option: {
        xAxis: {
          type: "category",
          data: ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"],
        },
        yAxis: {
          type: "value",
        },
        series: [
          {
            data: [150, 230, 224, 218, 135, 147, 260],
            type: "line",
          },
        ],
      },
    };
  },
});
</script>

<style lang="scss" scoped>
.echarts {
  width: 100%;
  height: 100%;
}
.about {
  width: 100%;
  height: 100%;
}
</style>
