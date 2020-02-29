<template>
  <div id="app">
    <div id="myChart"></div>
  </div>
</template>

<script>
export default {
  mounted() {
    this.drawLine()
  },
  methods: {
    drawLine() {
      var myChart = this.$echarts.init(document.getElementById('myChart'))

      // 指定图表的配置项和数据
      let option = {
        legend: {},
        tooltip: {},
        dataset: {
          source: [
            ['product', '2015', '2016', '2017'],
            ['Matcha Latte', 43.3, 85.8, 93.7],
            ['Milk Tea', 83.1, 73.4, 55.1],
            ['Cheese Cocoa', 86.4, 65.2, 82.5],
            ['Walnut Brownie', 72.4, 53.9, 39.1]
          ]
        },
        xAxis: { type: 'category' },
        yAxis: {},
        // Declare several bar series, each will be mapped
        // to a column of dataset.source by default.
        series: [{ type: 'bar' }, { type: 'bar' }, { type: 'bar' }]
      }

      // 使用刚指定的配置项和数据显示图表。
      myChart.setOption(option)
    }
  }
}
</script>

<style>
#myChart {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 50px;
  left: 0;
  padding: 10px;
}
</style>