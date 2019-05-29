<template>
  <div id="app">
    <div>
      <canvas id="horizontal_bar_chart"></canvas>
    </div>
  </div>
</template>
<script>
import Chart from "chart.js";
export default {
  methods: {
    createChart() {
      var ctx = document
        .getElementById("horizontal_bar_chart")
        .getContext("2d");

      var data = {
        labels: ["Budget"],
        datasets: [
          {
            label: "Low",
            data: [67.8],
            backgroundColor: "#D6E9C6" // green
          },
          {
            label: "High",
            data: [11.4],
            backgroundColor: "#EBCCD1" // red
          }
        ]
      };
      var options = {
        cornerRadius: 40,
        scales: {
          xAxes: [
            {
              stacked: true,
              gridLines: {
                display: false,
                drawBorder: false
              }
            }
          ],
          yAxes: [
            {
              stacked: true,
              gridLines: {
                display: false,
                drawBorder: false
              }
            }
          ]
        },
        legend: {
          display: true
        }
      };
      var horizontalBarChart = new Chart(ctx, {
        type: "horizontalBar",
        data: data,
        options: options
      });
    }
  },
  name: "app",
  data() {
    return {};
  },

  mounted() {
    this.createChart();
    let ckeditor = document.createElement("script");
    ckeditor.setAttribute("src", "./Chart.roundedBarCharts.js");
    document.head.appendChild(ckeditor);
  }
};
</script>

<style>
/* #guage-container {
  background-color: red;
  height: 200px;
}

#guage-o-meter {
  margin-top: -300px;
} */
</style>
