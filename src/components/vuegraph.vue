
<script>

import { Scatter } from "vue-chartjs";

export default {
  extends: Scatter,
  mounted() {
    this.renderChart(
      {
        datasets: [
          {
            label: "Scatter dataset 1",
            fill: false,
            borderColor: "black",
            pointBackgroundColor: "black",
            borderWidth: 1,
            pointBorderColor: "black",
            backgroundColor: this.gradient,
            showLine: true,
            data: [{x:1, y:50}, {x:2, y:2},{x:3, y:3}, {x:4, y:4}, {x:5, y:5}, {x:6, y:6}, {x:7, y:7}, {x:8, y:8}, {x:9, y:9}]
            
          },
        ]
      },
      
      {
        responsive: true,
        maintainAspectRatio: false,
            title: {
              display: true,
              text: "Osisoft PI data koppeling"
          }
      },
      
    );
  }
};



// import { Scatter } from "vue-chartjs";

// export default {
//   extends: Scatter,
//   mounted() {
//     this.renderChart(
//       {
//         labels: [
//           1,
//           2,
//           3,
//           4,
//           12,
//           15,
//           200
//         ],
//         datasets: [
//           {
//              label: "Data One",
//             borderColor: "#FC2525",
//             pointBackgroundColor: "white",
//             borderWidth: 1,
//             pointBorderColor: "white",
//             backgroundColor: this.gradient,
//             data: [40, 39, 10, 40, 39, 80, 40]
//           },
//           {
//             label: "Data Two",
//             borderColor: "#05CBE1",
//             pointBackgroundColor: "white",
//             pointBorderColor: "white",
//             borderWidth: 1,
//             backgroundColor: this.gradient2,
//             data: [60, 55, 32, 10, 2, 12, 53]
//           }
//         ]
//       },
//       {
//         responsive: true,
//         maintainAspectRatio: false,
//         title: {
//           display: true,
//           text: "My Data"
//         }
//       }
//     );
//   }
// };
</script>