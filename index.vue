<template>
  <div id="index" class="bg" ref="appRef">
      <Echart :options="zzoption" id="rightfirstEcharts" height="200px" width="200px"></Echart>
  </div>
</template>

<script>
import Echart from "@/common/echart";
import echarts from 'echarts'
export default {
  data() {
    return {
      option: {
        tooltip: {
          trigger: 'axis',
          axisPointer: {
            type: 'shadow'
          }
        },
        grid: {
          top: '10%',
          left: '3%',
          right: '4%',
          bottom: '10%',
          containLabel: true
        },
        xAxis: [
          {
            type: 'category',
            show: false,
            data: ['天', '大', '1'],
            axisTick: {
              alignWithLabel: false
            },
            axisLabel: {
              color: '#ffffff',
              fontSize: 16
            }
          }
        ],
        yAxis: [
          {
            show: false,
            type: 'value',
            interval: 20,
            axisLabel: {
              color: '#ffffff',
              fontSize: 16
            }
          },

        ],
        series: [
          {
            name: 'Direct',
            type: 'bar',
            data: [20, 42, 36],
            barGap: 0,
            barWidth: 13,
            label: {
              normal: {
                show: true,
                position: "top",
                color: '#fff'
              }
            },
            itemStyle: {
              normal: {
                // color: function (params) {//柱状图设置不同颜色
                //   // 给出颜色组
                //   var colorList = ["#00F294", "#00E7FC", "#FFC30E"];
                //   return colorList[params.dataIndex]
                // },
                color: function (params) {
                  let colorList = [
                  ['#00F294', '#03753E'],
                  ['#00E7FC', '#05609B'],
                  ['#FFC30E', '#9A7505']
                  ];
                  let colorItem = colorList[params.dataIndex];
                  return new echarts.graphic.LinearGradient(0, 0, 0, 1, //y->y2
                    [
                      {
                        offset: 0,
                        color: colorItem[0]
                      },
                      {
                        offset: 1,
                        color: colorItem[1]
                      }
                    ],
                    false
                  );
                }
              }
            },
          },
          {
            name: 'Direct',
            type: 'bar',
            barWidth: 16,
            data: [20, 42, 36],
            tooltip: {
              show: false
            },
            label: {
              normal: {
                show: false,
                position: "top",
              },
            },
            itemStyle: {
              normal: {
                // color: function (params) {//柱状图设置不同颜色
                //   // 给出颜色组
                //   var colorList = ["#00F294", "#00E7FC", "#FFC30E"];
                //   return colorList[params.dataIndex]
                // },
                color: function (params) {
                  let colorList = [
                  ['#00F294', '#03753E'],
                  ['#00E7FC', '#05609B'],
                  ['#FFC30E', '#9A7505']
                  ];
                  let colorItem = colorList[params.dataIndex];
                  return new echarts.graphic.LinearGradient(0, 0, 0, 1, //y->y2
                    [
                      {
                        offset: 0,
                        color: colorItem[0]
                      },
                      {
                        offset: 1,
                        color: colorItem[1]
                      }
                    ],
                    false
                  );
                }
              }
            },
          }, {
            name: 'Direct',
            barWidth: 22,
            data: [20, 42, 36],
            type: "pictorialBar", // 长方体顶部四边形
            symbol: 'diamond',
            symbolRotate: 0,
            symbolSize: ['28', '10'],
            symbolOffset: ['0', '-5'],
            symbolPosition: 'end',
            z: 3, // 顶部四边形
            tooltip: {
              show: false
            },
            label: {
              normal: {
                show: false,
                position: "insideRight"
              }
            },
            itemStyle: {
              // color: function(params) {//柱状图设置不同颜色
              //   // 给出颜色组
              //     var colorList = ["#00F294", "#00E7FC", "#FFC30E"];
              //     return colorList[params.dataIndex]
              //   },
              //设置渐变
              color: function (params) {
                let colorList = [
                  ['#00F294', '#03753E'],
                  ['#00E7FC', '#05609B'],
                  ['#FFC30E', '#9A7505']
                ];
                let colorItem = colorList[params.dataIndex];
                return new echarts.graphic.LinearGradient(0, 0, 0, 1, //y->y2
                  [
                    {
                      offset: 0,
                      color: colorItem[0]
                    },
                    {
                      offset: 1,
                      color: colorItem[1]
                    }
                  ],
                  false
                );
              }
            },
          },

        ]
      }
    };
  },
  components: {
    Echart,
  },
  mounted() {},
  beforeDestroy() { },
  methods: {},
};
</script>

