<template>
  <section>
    <div class="item left">
      <panel-item>
        <div ref="leftOne" class="panel"></div>
      </panel-item>
      <panel-item>
        <div ref="leftTWO" class="panel"></div>
      </panel-item>
      <panel-item>
        <div ref="leftThree" class="panel"></div>
      </panel-item>
    </div>
    <div class="item center">
      <center-top></center-top>
      <center-content> </center-content>
    </div>
    <div class="item right">
      <panel-item>
        <div ref="rightOne" class="panel"></div>
      </panel-item>
      <panel-item>
        <div ref="rightTWO" class="panel"></div>
      </panel-item>
      <panel-item>
        <div ref="rightThree" class="panel"></div>
      </panel-item>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import centerTop from "@/components/centerTop";
import centerContent from "@/components/centerContent";
import panelItem from "@/components/panelItem";
import echarts from "../utils/globalEcharts.js";

const leftOne = ref(null);
const leftTWO = ref(null);
const leftThree = ref(null);
const rightOne = ref(null);
const rightTWO = ref(null);
const rightThree = ref(null);
const centerMap = ref(null);

onMounted(() => {
  // 左侧第一个柱状图
  const leftOneChart = echarts.init(leftOne.value);
  const leftOneOptions = {
    title: {
      text: "柱状图-就业行业",
      left: "center",
      top: "5%",
      textStyle: {
        color: "#fff",
        fontSize: 15,
      },
    },
    tooltip: {
      trigger: "axis",
      backgroundColor: "rgba(39, 42, 59,.6)",
      borderColor: "rgba(51, 51, 51, 0.01)",
      textStyle: {
        fontSize: 10,
        color: "white",
      },
      axisPointer: {
        type: "shadow",
        lineStyle: {},
      },
    },
    grid: {
      left: "10%",
      right: "10%",
      bottom: "15%",
      top: "20%",
    },
    xAxis: [
      {
        type: "category",
        data: [
          "旅游行业",
          "游戏行业",
          "电商行业",
          "金融行业",
          "网络行业",
          "厨师行业",
          "服务行业",
        ],
        // 不显示x轴的线
        axisLine: {
          show: false,
        },
        // 是否显示刻度
        axisTick: {
          show: false,
        },
        // 坐标轴上的标签
        axisLabel: {
          textStyle: {
            color: "rgba(255,255,255,.6)",
            fontSize: "9",
          },
        },
      },
    ],
    yAxis: {
      type: "value",
      // 分割线的样式
      splitLine: {
        lineStyle: {
          color: "rgba(255,255,255,.1)",
        },
      },
      axisLine: {
        show: true,
        lineStyle: {
          color: "rgba(255,255,255,.3)",
        },
      },
    },
    series: [
      {
        data: [200, 300, 300, 900, 1500, 1200, 600],
        type: "bar",
        barWidth: 20,
        itemStyle: {
          color: "rgba(57, 111, 228, 1)",
          borderRadius: [4, 4, 0, 0],
        },
      },
    ],
  };
  leftOneChart.setOption(leftOneOptions);
  // 右侧第一个柱状图
  const myColor = ["#1089E7", "#F57474", "#56D0E3", "#F8B448", "#8B78F6"];
  const rightOneChart = echarts.init(rightOne.value);
  const rightOneOptions = {
    title: {
      text: "柱状图-技能掌握",
      left: "center",
      top: "8%",
      textStyle: {
        color: "#fff",
        fontSize: 15,
      },
    },
    // tooltip: {
    //   trigger: "axis",
    //   backgroundColor: "rgba(39, 42, 59,.6)",
    //   borderColor: "rgba(51, 51, 51, 0.01)",
    //   textStyle: {
    //     fontSize: 10,
    //     color: "white",
    //   },
    //   axisPointer: {
    //     type: "shadow",
    //   },
    // },

    grid: {
      left: "8%",
      right: "5%",
      bottom: "3%",
      containLabel: true,
    },
    xAxis: {
      show: false,
      type: "value",
    },
    yAxis: [
      {
        type: "category",
        // 坐标轴是否显示
        axisLine: {
          show: false,
        },
        // 刻度是否显示
        axisTick: {
          show: false,
        },
        // 去除分割线
        splitLine: {
          show: false,
        },
        // 刻度标签样式
        axisLabel: {
          fontSize: 12,
          color: "#fff",
        },
        data: ["HTML5", "CSS3", "Javascript", "VUE", "NODE"],
      },
      {
        data: [702, 350, 610, 793, 664],
        axisTick: {
          show: false,
        },
        axisLine: {
          show: false,
        },
        axisLabel: {
          fontSize: 12,
          color: "#fff",
        },
      },
    ],
    series: [
      {
        name: "轴",
        type: "bar",
        yAxisIndex: 0,
        barWidth: 10,
        itemStyle: {
          color: function (params) {
            var num = myColor.length;
            return myColor[params.dataIndex % num];
          },
          barBorderRadius: 20,
        },
        data: [70, 34, 60, 78, 69],
      },
      {
        name: "框",
        type: "bar",
        yAxisIndex: 1,
        barWidth: 15,
        itemStyle: {
          color: "none",
          borderColor: "#00c1de",
          borderWidth: 3,
          barBorderRadius: 15,
        },
        data: [100, 100, 100, 100, 100],
      },
    ],
  };
  rightOneChart.setOption(rightOneOptions);
  // 左侧第二个折线图
  const leftTwoChart = echarts.init(leftTWO.value);
  const leftTwoOptions = {
    color: ["#00f2f1", "#ed3f35"],
    title: {
      text: "折线图-人员变化",
      left: "center",
      top: "5%",
      textStyle: {
        color: "#fff",
        fontSize: 15,
      },
    },
    // 提示框样式
    tooltip: {
      trigger: "axis",
      backgroundColor: "rgba(39, 42, 59,.6)",
      borderColor: "rgba(51, 51, 51, 0.01)",
      formatter: "{a}<br/>{b} : {c}",
      textStyle: {
        fontSize: 10,
        color: "white",
      },
    },
    legend: {
      top: "12%",
      right: "5%",
      textStyle: {
        color: "#3e7afa",
        fontSize: "9",
      },
    },
    // 坐标系距离外侧的距离
    grid: {
      left: "3%",
      right: "10%",
      bottom: "3%",
      containLabel: true,
    },
    xAxis: {
      type: "category",
      boundaryGap: false,
      axisTick: {
        show: false,
      },
      data: ["一月", "三月", "五月", "七月", "九月", "十一月"],
    },
    yAxis: {
      type: "value",
      // 修改y轴分割线的颜色
      splitLine: {
        lineStyle: {
          color: "#012f4a",
        },
      },
    },
    series: [
      {
        name: "新增粉丝",
        type: "line",
        stack: "Total",
        smooth: "true",
        data: [24, 40, 101, 134, 90, 230, 210, 230, 120, 230, 210, 120],
      },
      {
        name: "新增游客",
        type: "line",
        stack: "Total",
        smooth: "true",
        data: [40, 64, 191, 324, 290, 330, 310, 213, 180, 200, 180, 79],
      },
    ],
  };
  leftTwoChart.setOption(leftTwoOptions);
  // 右侧第二个折线图
  const rightTwoChart = echarts.init(rightTWO.value);
  const rightTwoOptions = {
    title: {
      text: "折线图-播放量",
      left: "center",
      top: "5%",
      textStyle: {
        color: "#fff",
        fontSize: 15,
      },
    },
    // 提示框
    tooltip: {
      trigger: "axis",
      backgroundColor: "rgba(39, 42, 59,.6)",
      borderColor: "rgba(51, 51, 51, 0.01)",
      textStyle: {
        fontSize: 10,
        color: "white",
      },
    },
    legend: {
      data: ["播放量", "转发量"],
      right: 10,
      top: 30,
      textStyle: {
        color: "#fff",
        fontSize: "10",
      },
    },
    grid: {
      left: "3%",
      right: "4%",
      bottom: "5%",
      containLabel: true,
    },
    xAxis: [
      {
        type: "category",
        boundaryGap: false,
        data: [
          "01",
          "02",
          "03",
          "04",
          "05",
          "06",
          "07",
          "08",
          "09",
          "11",
          "12",
          "13",
          "14",
          "15",
          "16",
          "17",
          "18",
          "19",
          "20",
          "21",
          "22",
          "23",
          "24",
          "25",
          "26",
          "27",
          "28",
          "29",
          "30",
        ],
      },
    ],
    yAxis: [
      {
        type: "value",
        splitLine: {
          show: false,
        },
      },
    ],
    series: [
      {
        name: "播放量",
        type: "line",
        smooth: true,
        lineStyle: {
          width: 0,
        },
        showSymbol: false,
        areaStyle: {
          opacity: 0.8,
          color: new echarts.graphic.LinearGradient(
            0,
            0,
            0,
            1,
            [
              {
                offset: 0,
                color: "rgba(0, 216, 135, 0.4)",
              },
              {
                offset: 0.8,
                color: "rgba(0, 216, 135, 0.1)",
              },
            ],
            false
          ),
        },
        emphasis: {
          focus: "series",
        },
        data: [
          30, 40, 30, 40, 30, 40, 30, 60, 20, 40, 20, 40, 30, 40, 30, 40, 30,
          40, 30, 60, 20, 40, 20, 40, 30, 60, 20, 40, 20, 40,
        ],
      },
      {
        name: "转发量",
        type: "line",
        smooth: true,
        lineStyle: {
          width: 0,
        },
        showSymbol: false,
        label: {
          show: true,
          position: "top",
        },
        areaStyle: {
          opacity: 0.8,
          color: new echarts.graphic.LinearGradient(
            0,
            0,
            0,
            1,
            [
              {
                offset: 0,
                color: "rgba(1, 132, 213, 0.4)",
              },
              {
                offset: 0.8,
                color: "rgba(1, 132, 213, 0.1)",
              },
            ],
            false
          ),
        },
        emphasis: {
          focus: "series",
        },
        data: [
          50, 30, 50, 60, 10, 50, 30, 50, 60, 40, 60, 40, 80, 30, 50, 60, 10,
          50, 30, 70, 20, 50, 10, 40, 50, 30, 70, 20, 50, 10, 40,
        ],
      },
    ],
  };
  rightTwoChart.setOption(rightTwoOptions);
  // 左侧第三个饼状图
  const LeftThreeChart = echarts.init(leftThree.value);
  const leftThreeOptions = {
    // 设置标题
    title: {
      text: "饼形图-年龄分布",
      textStyle: {
        color: "white",
        fontSize: 15,
      },
      top: "7%",
      left: "center",
    },
    // 设置提示框的样式
    tooltip: {
      trigger: "item",
      backgroundColor: "rgba(39, 42, 59,.6)",
      borderColor: "rgba(51, 51, 51, 0.01)",
      formatter: "{a}<br/>{b} : {c} ({d}%)",
      textStyle: {
        color: "white",
        fontSize: 10,
      },
    },
    // echarts距离边缘的大小
    legend: {
      top: "85%",
      left: "center",
      textStyle: {
        fontSize: 12,
        color: "rgba(255,255,255,.5)",
      },
      // 下面标签的大小
      itemWidth: 10,
      itemHeight: 10,
    },
    series: [
      {
        name: "年龄分布",
        type: "pie",
        radius: ["30%", "48%"],
        center: ["50%", "50%"],
        color: [
          "#065aab",
          "#066eab",
          "#0682ab",
          "#0696ab",
          "#06a0ab",
          "#06b4ab",
          "#06c8ab",
          "#06dcab",
          "#06f0ab",
        ],
        label: {
          show: false,
          position: "top",
        },
        // 选中之后label的变化
        emphasis: {
          label: {
            show: true,
            fontSize: "20",
            fontWeight: "naomal",
          },
        },
        // 是否显示视觉引导线
        labelLine: {
          show: false,
        },
        data: [
          { value: 1, name: "0岁以下" },
          { value: 4, name: "20-29岁" },
          { value: 2, name: "30-39岁" },
          { value: 2, name: "40-49岁" },
          { value: 1, name: "50岁以上" },
        ],
      },
    ],
  };
  LeftThreeChart.setOption(leftThreeOptions);
  const rightThreeChart = echarts.init(rightThree.value);
  const rightThreeOptions = {
    // 是否显示标题
    title: {
      text: "饼形图-地区分布",
      left: "center",
      top: "7%",
      textStyle: {
        color: "white",
        fontSize: 15,
      },
    },
    // 下面标签距离
    legend: {
      bottom: "5%",
      itemWidth: 10,
      itemHeight: 10,
      textStyle: {
        fontSize: 12,
        color: "rgba(255,255,255,.5)",
      },
    },
    // 工具栏是否显示
    toolbox: {
      show: true,
      iconStyle: {},
      feature: {
        saveAsImage: { show: true },
      },
    },
    // 提示框样式
    tooltip: {
      trigger: "item",
      backgroundColor: "rgba(39, 42, 59,.6)",
      borderColor: "rgba(51, 51, 51, 0.01)",
      formatter: "{a}<br/>{b} : {c} ({d}%)",
      textStyle: {
        fontSize: 10,
        color: "white",
      },
    },
    color: [
      "#006cff",
      "#60cda0",
      "#ed8884",
      "#ff9f7f",
      "#0096ff",
      "#9fe6b8",
      "#32c5e9",
      "#1d9dff",
    ],
    series: [
      {
        name: "地区分布",
        type: "pie",
        radius: [10, 60],
        center: ["50%", "50%"],
        roseType: "area",
        itemStyle: {
          borderRadius: 0,
        },
        data: [
          { value: 20, name: "云南" },
          { value: 26, name: "北京" },
          { value: 24, name: "山东" },
          { value: 25, name: "河北" },
          { value: 20, name: "江苏" },
          { value: 25, name: "浙江" },
          { value: 30, name: "深圳" },
          { value: 42, name: "广东" },
        ],
        // 提示标签
        label: {
          color: "rgba(255,255,255,.5)",
          fontSize: 12,
        },
        // 提示的标签连接的引导线
        labelLine: {
          length: 8,
          length2: 8,
        },
      },
    ],
  };
  rightThreeChart.setOption(rightThreeOptions);
  // 监听页面实现响应式
  window.onresize = function () {
    leftOneChart.resize();
    rightOneChart.resize();
    leftTwoChart.resize();
    rightTwoChart.resize();
    LeftThreeChart.resize();
    rightThreeChart.resize();
  };
});
</script>

<style lang="less" scoped>
section {
  display: flex;
  padding: 1.1667vw 1vw 0;
  border: 0.1333vw solid #ccc;
  .item {
    flex: 3;
    &:nth-child(2) {
      flex: 5;
    }
    .panel {
      width: 26.6667vw;
      height: 16.4vw;
    }
  }
  .left,
  .right {
    width: 26.6667vw;
    height: 50.6667vw;
  }
  .center {
    display: flex;
    flex-direction: column;
    padding: 0 0.8vw;
  }
}
</style>
