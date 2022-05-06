<template>
  <el-container stripe
                v-loading="loading"
                element-loading-text="拼命加载中"
                element-loading-spinner="el-icon-loading"
                element-loading-background="rgba(0, 0, 0, 0.5)">
    <el-header >粉丝数量</el-header>
    <el-container>
      <el-container>
        <el-aside width="430px"> <ve-radar :data="chartData" height="450px" style="margin-top: 30px"></ve-radar></el-aside>
        <el-main>
          <el-card class="box-card1">
            <ve-histogram :data="chartData_1"  height="300px"></ve-histogram>
          </el-card>
          <el-card class="box-card">
            <ve-pie :data="chartData_2" height="300px"></ve-pie>
          </el-card>
        </el-main>
      </el-container>
    </el-container>

<!--    <el-main>-->
<!--      <div style="display: inline; float: left; width: 44%; height: 800px; ">-->
<!--        <ve-line :data="chartData"  height="400px"></ve-line>-->
<!--      </div>-->
<!--      <div style="display: inline;float: right; width: 44%;margin-left:-100px ">-->
<!--      </div>-->
<!--    </el-main>-->
  </el-container>
</template>

<script>
export default {
  name: 'fans',
  loading:true,
  data: function () {
    return {
      chartData: {
        columns: ['平台', '原粉丝数', '现粉丝数', '粉丝增长率'],
        rows: [
          { '平台': '知乎', '原粉丝数': 1393, '现粉丝数': 1093, '粉丝增长率': 0.32 },
          { '平台': '微博', '原粉丝数': 3530, '现粉丝数': 3230, '粉丝增长率': 0.26 },
          { '平台': '头条', '原粉丝数': 2923, '现粉丝数': 2623, '粉丝增长率': 0.76 },
          { '平台': '小红书', '原粉丝数': 1723, '现粉丝数': 1423, '粉丝增长率': 0.49 },
          { '平台': 'b站', '原粉丝数': 3792, '现粉丝数': 3492, '粉丝增长率': 0.323 },
          { '平台': '抖音', '原粉丝数': 4593, '现粉丝数': 4293, '粉丝增长率': 0.78 }
        ]
      },
      chartData_1: {
        columns: ['日期', '原粉丝数', '现粉丝数', '粉丝增长率'],
        rows: [
          { '日期': '1/1', '原粉丝数': 1393, '现粉丝数': 1093, '粉丝增长率': 0.32 },
          { '日期': '1/2', '原粉丝数': 3530, '现粉丝数': 3230, '粉丝增长率': 0.26 },
          { '日期': '1/3', '原粉丝数': 2923, '现粉丝数': 2623, '粉丝增长率': 0.76 },
          { '日期': '1/4', '原粉丝数': 1723, '现粉丝数': 1423, '粉丝增长率': 0.49 },
          { '日期': '1/5', '原粉丝数': 3792, '现粉丝数': 3492, '粉丝增长率': 0.323 },
          { '日期': '1/6', '原粉丝数': 4593, '现粉丝数': 4293, '粉丝增长率': 0.78 }
        ]
      },
      chartData_2: {
        columns: ['年龄分布', '原粉丝数', '现粉丝数', '粉丝增长率'],
        rows: [
          { '年龄分布': '10岁以下', '原粉丝数': 1393, '现粉丝数': 1093, '粉丝增长率': 0.32 },
          { '年龄分布': '10岁到15岁', '原粉丝数': 3530, '现粉丝数': 3230, '粉丝增长率': 0.26 },
          { '年龄分布': '15岁到20岁', '原粉丝数': 2923, '现粉丝数': 2623, '粉丝增长率': 0.76 },
          { '年龄分布': '20岁到30岁', '原粉丝数': 1723, '现粉丝数': 1423, '粉丝增长率': 0.49 },
          { '年龄分布': '30岁以上', '原粉丝数': 3792, '现粉丝数': 3492, '粉丝增长率': 0.323 },
          { '年龄分布': '50岁以上', '原粉丝数': 4593, '现粉丝数': 4293, '粉丝增长率': 0.78 }
        ]
      }
    }
  },
  created(){
    setTimeout(() => {
      this.$data.loading=false;
    }, 500);

  },
}
</script>


<style scoped>
@import url("fans.css");
</style>
