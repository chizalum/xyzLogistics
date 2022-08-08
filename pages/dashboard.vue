<template>
  <div>
    <div class="fullpage">
      <h1 class="welcome">Welcome back David</h1>
      <div class="stats">
        <div class="revenue">
          <p class="total">Total Revenue</p>
          <p class="amount">₦200k</p>
          <div class="facts">
            <p class="up">Up by 50k this month</p>
            <img src="greenarrow.png" alt="uparrow" class="greenarrow" />
          </div>
        </div>
        <div class="active">
          <p class="order">Active Orders</p>
          <p class="twohundred">200</p>
          <div class="fact">
            <p class="down">Down by 50k this month</p>
            <img src="redarrow.png" alt="downarrow" class="redarrow" />
          </div>
        </div>
        <div class="pending">
          <p class="pend">Pending Orders</p>
          <p class="fournine">49</p>
        </div>
        <div class="riders">
          <p class="ride">Active Riders</p>
          <p class="seveno">70</p>
        </div>
      </div>
      <hr class="horizontalrule" />
      <div class="barchartdiv">
        <BarChart
          :chartData="chartData"
          :options="chartOptions"
          class="bar-chart"
        />
      </div>
      <div class="vehiclesdiv">
        <LineChart
          :chartData="lineChartData"
          :options="linechartOptions"
          class="line-chart"
        />
        <PieChart
          :chartData="pieChartData"
          :options="piechartOptions"
          class="pie-chart"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "dashboard",

  data() {
    return {
      lineChartData: {
        labels: [
          "JAN",
          "FEB",
          "MAR",
          "APRIL",
          "MAY",
          "JUNE",
          "JULY",
          "AUG",
          "SEPT",
        ],
        datasets: [
          {
            label: "Damaged vehicles per month",
            backgroundColor: "white",
            borderColor: "rgba(255,99,132,1)",
            borderWidth: 1,
            hoverBackgroundColor: "rgba(255,99,132,0.4)",
            hoverBorderColor: "rgba(255,99,132,1)",
            data: [100, 50, 65, 75, 52, 50, 200, 150, 170],
          },
        ],
      },
      pieChartData: {
        labels: ["Trucks (23 trucks)", "Vans (30 vans)", "Bikes(200 bikes)"],
        datasets: [
          {
            label: "No. Damaged Vehicles",
            data: [23, 30, 200],
            backgroundColor: ["#FFD60A", "#7FB069", "#CC5500"],
            hoverBackgroundColor: ["#FFD60A", "#7FB069", "#CC5500"],
          },
        ],
      },

      chartData: {
        labels: [
          "Dec 21",
          "Dec 22",
          "Dec 23",
          "Dec 24",
          "Dec 25",
          "Dec 26",
          "Dec 27",
          "Dec 28",
          "Dec 29",
          "Dec 30",
          "Dec 31",
          "Jan 01",
          "Jan 02",
          "Jan 03",
          "Jan 04",
          "Jan 05",
          "Jan 06",
        ],
        datasets: [
          {
            label: "Monthly Revenue",
            backgroundColor: "rgba(217, 182, 8, 1)",
            borderColor: "rgba(217, 182, 8, 1)",
            borderWidth: 0,
            fill: false,
            hoverBackgroundColor: "rgba(255,99,132,0.4)",
            hoverBorderColor: "rgba(255,99,132,1)",
            data: [
              50, 80, 50, 70, 60, 45, 55, 65, 55, 48, 55, 45, 50, 70, 80, 45,
              55,
            ],
          },
        ],
      },
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          xAxes: [
            {
              gridLines: {
                display: false,
              },
            },
          ],
          yAxes: [
            {
              ticks: {
                beginAtZero: true,
                display: false,
                font: {
                  size: 14,
                  family: "DM Sans",
                  weight: "bold",
                },
              },
              gridLines: {
                display: false,
              },
            },
          ],
        },
        tooltips: {
          backgroundColor: "#ffffff",
          titleFontColor: "#ffffff",
          bodyFontColor: "#ffffff",
          bodySpacing: 0,
          xPadding: 0,
        },
      },

      linechartOptions: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          xAxes: [
            {
              gridLines: {
                display: false,
              },
            },
          ],
          yAxes: [
            {
              ticks: {
                beginAtZero: true,
                display: true,
                font: {
                  size: 12,
                  family: "DM Sans",
                  weight: "regular",
                },
              },
              gridLines: {
                display: false,
              },
            },
          ],
        },
        tooltips: {
          backgroundColor: "#ffffff",
          titleFontColor: "#ffffff",
          bodyFontColor: "#ffffff",
          bodySpacing: 0,
          xPadding: 0,
        },
      },

      piechartOptions: {
        responsive: true,
        maintainAspectRatio: false,
        tooltips: {
          backgroundColor: "#ffffff",
          titleFontColor: "#ffffff",
          bodyFontColor: "#ffffff",
          bodySpacing: 0,
          xPadding: 0,
        },
        ticks: {
          beginAtZero: true,
          display: false,
          font: {
            size: 12,
            family: "DM Sans",
            weight: "regular",
          },
        },
        datasets: [{}],
      },
    };
  },
};
</script>

<style scoped>
.bar-chart {
  margin: 0 0 0 0;
  height: 379px;
  width: 984px;
  background-color: #ffffff;
}

.line-chart {
  margin: 0 0 0 0;
  height: 240px;
  width: 545px;
  background-color: #ffffff;
}

.pie-chart {
  margin: 0 0 0 58px;
  height: 240px;
  width: 381px;
  background-color: #ffffff;
}

.welcome {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 25px;
  line-height: 40px;
  color: #000000;
  margin: 96px 0 0 344px;
}

.stats {
  display: flex;
  flex-direction: row;
  margin: 40px 0 0 368px;
  padding: 0;
  white-space: nowrap;
}

.revenue {
  width: 260px;
  height: 125px;
  left: 344px;
  top: 152px;
  border-right: 1px solid #f3f3f3;
  padding: 24px 0 0 24px;
  margin: 0;
  display: flex;
  flex-direction: column;
}

.active {
  width: 260px;
  height: 125px;
  left: 344px;
  top: 152px;
  border-right: 1px solid #f3f3f3;
  padding: 24px 0 0 24px;
  margin: 0;
  display: flex;
  flex-direction: column;
}

.pending {
  width: 260px;
  height: 125px;
  left: 344px;
  top: 152px;
  border-right: 1px solid #f3f3f3;
  padding: 24px 0 0 24px;
  margin: 0;
  display: flex;
  flex-direction: column;
}

.riders {
  width: 260px;
  height: 125px;
  left: 344px;
  top: 152px;
  border-right: 1px solid #f3f3f3;
  padding: 24px 0 0 24px;
  margin: 0;
  display: flex;
  flex-direction: column;
}

.total {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 21px;
  color: #000000;
  margin: 0 0 0 0;
}

.amount {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 700;
  font-size: 40px;
  color: #000000;
  margin: 13px 0 0 0;
  line-height: 56px;
}

.facts {
  display: flex;
  flex-direction: row;
  margin: 15px 0 0 0;
  align-items: center;
  height: 18.24px;
}

.up {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 21px;
  color: #adadad;
}

.greenarrow {
  width: 18.24px;
  height: 18.24px;
  margin: 0 0 0 10.88px;
}

.order {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 21px;
  color: #000000;
  margin: 0 0 0 0;
}

.twohundred {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 700;
  font-size: 40px;
  line-height: 56px;
  color: #000000;
  margin: 13px 0 0 0;
  padding: 0;
}

.fact {
  display: flex;
  flex-direction: row;
  margin: 15px 0 0 0;
  height: 18.24px;
}

.down {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 21px;
  color: #adadad;
  margin: 0 0 0 0;
}

.redarrow {
  height: 18.24px;
  width: 18.24px;
  margin: 0 0 0 10.88px;
}

.pend {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 21px;
  color: #000000;
  margin: 0 0 0 0;
}

.fournine {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 700;
  font-size: 40px;
  line-height: 56px;
  color: #000000;
  margin: 13px 0 0 0;
}

.ride {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 21px;
  color: #000000;
  margin: 0 0 0 0;
}

.seveno {
  font-family: "DM Sans";
  font-style: normal;
  font-weight: 700;
  font-size: 40px;
  line-height: 56px;
  color: #000000;
  margin: 13px 0 0 0;
}

.horizontalrule {
  margin: 30px 0 0 320px;
  width: 1044px;
  color: #f3f3f3;
  border: 1px solid #f3f3f3;
}

.barchartdiv {
  margin: 32px 0 0 344px;
  padding: 0;
  border: none;
  width: 984px;
  height: 379px;
  object-fit: cover;
}

.vehiclesdiv {
  width: 984px;
  margin: 32px 0 0 344px;
  display: flex;
  flex-direction: row;
  align-content: space-between;
}
</style>
