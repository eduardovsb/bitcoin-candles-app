<template>
  <apexchart
    type="candlestick"
    height="350"
    :options="chartOptions"
    :series="series"
  ></apexchart>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import { Prop } from 'vue-property-decorator';
import VueApexCharts from 'vue3-apexcharts';

@Options({
  components: {
    apexchart: VueApexCharts,
  },
})
export default class CandleStickChart extends Vue {
  @Prop()
  candles!: [];

  chartOptions = {
    chart: {
      type: 'candlestick',
      height: 350,
    },
    title: {
      text: 'Bitcoin Last Prices',
      align: 'left',
    },
    xaxis: {
      type: 'time',
    },
    yaxis: {
      tooltip: {
        enabled: true,
      },
    },
  };

  get series() {
    const series = [
      {
        data: this.candles,
      },
    ];

    return series;
  }
}
</script>

<style></style>
