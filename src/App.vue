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
        labels: ["Red", "Blue", "Yellow", "Green", "Purple", "Orange"],
        datasets: [
          {
            label: "% change in support",
            data: [12, -19, -3, 5, 2, 3],
            backgroundColor: [
              "rgba(255, 99, 132, 1)",
              "rgba(54, 162, 235, 1)",
              "rgba(255, 206, 86, 1)",
              "rgba(75, 192, 192, 1)",
              "rgba(153, 102, 255, 1)",
              "rgba(255, 159, 64, 1)"
            ],
            borderWidth: 0
          }
        ]
      };
      var options = {
        cornerRadius: 20,
        scales: {
          yAxes: [
            {
              ticks: {
                beginAtZero: true
              }
            }
          ]
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
    return {
    };
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
