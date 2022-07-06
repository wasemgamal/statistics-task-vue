<template>
  <div
    style="
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      padding: 30px;
    "
  >
    <aside style="width: 400px">
      <apexchart
        width="100%"
        height="300"
        type="line"
        :options="visits.options"
        :series="visits.series"
      ></apexchart>
    </aside>
    <aside style="width: 400px">
      <apexchart
        width="100%"
        height="300"
        type="pie"
        :options="devices.options"
        :series="devices.series"
      ></apexchart>
    </aside>
    <aside style="width: 400px">
      <apexchart
        width="100%"
        height="300"
        type="bar"
        :options="profits.options"
        :series="profits.series"
      ></apexchart>
    </aside>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      visits: {
        options: {
          chart: {
            id: "visits-chart",
          },
          xaxis: {
            title: {
                text: 'Countries'
            },
            categories: ['Egypt', 'Saudi Arabia', 'Qatar', 'Kuwit'],
          },
          yaxis: {
            title: {
                text: 'Visits'
            },
            categories: ['Egypt', 'Saudi Arabia', 'Qatar', 'Kuwit'],
          },
        },
        series: [{
              name: "Visits",
              data: [10, 41, 35, 51]
          }],
      },
      devices: {
        options: {
          labels: ['IOS', 'Web', 'Android'],
        },
        series: [44, 55, 13],
      },
      profits: {
        options: {
          chart: {
            id: "profits-chart",
          },
          xaxis: {
            title: {
                text: 'Years'
            },
            categories: [2000, 2001, 2002, 2003, 2004, 2005, 2006, 2007],
          },
          yaxis: {
            title: {
                text: 'Profits in $'
            },
          },
        },
        series: [
          {
            name: "series-1",
            data: [300, 400, 450, 500, 490, 600, 700, 910],
          },
        ],
      },
    };
  },
};
</script>