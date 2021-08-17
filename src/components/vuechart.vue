<template>
  <div class="columns module">
    <div class="controls column-4">
      <div class="control">
        <button class="button is-primary" @click="addData()">add data</button>
      </div>
      <div class="control">
        <input
          class="input is-success"
          type="color"
          v-model="chart.traces[0].line.color"
        />
      </div>
      <div class="control">
        <input
          class="input is-success"
          type="text"
          v-model="chart.layout.xaxis.title"
        />
      </div>
      <div class="control">
        <input
          class="input is-success"
          type="text"
          v-model="chart.layout.yaxis.title"
        />
      </div>

      <div class="control">
        <input
          class="input"
          type="number"
          min="2"
          max="10"
          v-model="chart.traces[0].line.width"
        />
      </div>
      <div class="control">
        <div class="select">
          <select v-model="chart.traces[0].line.shape">
            <option value="line">line</option>
            <option value="spline">spline</option>
            <option value="hv">hv</option>
          </select>
        </div>
      </div>
    </div>
    <div class="chart-container column">
      <reactive-chart :chart="chart"></reactive-chart>
    </div>
  </div>
</template>

<script>
export default {
  props: ["chart"],
  template: '<div :ref="chart.uuid"></div>',
  mounted() {
    Plotly.plot(
      this.$refs[this.chart.uuid],
      this.chart.traces,
      this.chart.layout
    );
    for (let i = 0; i < 100; i++) {
      this.addData();
    }
  },
  watch: {
    chart: {
      handler: function () {
        Plotly.react(
          this.$refs[this.chart.uuid],
          this.chart.traces,
          this.chart.layout
        );
      },
      deep: true,
    },
  },
  methods: {
    addData: function () {
      this.chart.layout.datarevision = new Date().getTime();
      this.chart.traces[0].y.push(Math.random());
    },
  },
  data() {
    return {
      chart: {
        uuid: "123",
        traces: [
          {
            y: [],
            line: {
              color: "#5e9e7e",
              width: 4,
              shape: "line",
            },
          },
        ],
        layout: {
          title: "reactive charts",
          xaxis: {
            title: "xaxis title",
          },
          yaxis: {
            title: "yaxis title",
          },
        },
      },
    };
  },
};
</script>

<style>
</style>


  

  