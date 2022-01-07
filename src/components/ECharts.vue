<template>
  <div class="echarts" :id="id"></div>
</template>
<script lang="ts">
import { defineComponent, onBeforeUnmount, onMounted } from "vue";
import * as echarts from "echarts";

export default defineComponent({
  name: "ECharts",
  props: {
    options: {
      type: Object,
      default: () => ({}),
    },
  },
  setup(ctx) {
    const id = "echarts-1";
    let chart: any = null;

    const initEcharts = () => {
      if (!chart) {
        const dom: any = document.getElementById(id);
        chart = echarts.init(dom);
      } else {
        return;
      }
      if (!ctx.options) return;
      console.log(ctx.options);
      chart.setOption(ctx.options);
    };
    const eventListener = () => {
      if (chart) {
        chart.resize();
      }
    };
    onMounted(() => {
      initEcharts();
      // debugger;
      window.addEventListener("resize", eventListener);
    });

    onBeforeUnmount(() => {
      window.removeEventListener("resize", eventListener);
    });

    return {
      id,
    };
  },
});
</script>

<style lang="scss" scoped>
.echarts {
  width: 100%;
  height: 100%;
}
</style>
