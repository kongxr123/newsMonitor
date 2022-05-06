<template>
  <div>
    <div class="box7">
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <span>微博</span>
        <el-button style="float: right; padding: 3px 0" type="text">操作按钮</el-button>
      </div>
      <el-header>
        <div class="title1">2,407,485</div>
        <div class="title2">最新热度</div>
      <div class="line"/>
        <div class="title3">238.1</div>
        <div class="title4">上升速度</div>
        <div class="line1"/>
        <div class="title5">1.0h</div>
        <div class="title6">在榜时长</div>
      </el-header>
      <div v-for="(item,index) in items" :key="item" class="text item">
        {{index}}--{{item}}
      </div>
      <div class="block">
        <div class="box">
        <span>节点</span>
        <span style="margin-left: 60px">排名</span>
        <span style="margin-left: 60px">热度</span>
        </div>
        <div class="box1">
        <el-timeline :reverse="reverse">
          <el-timeline-item
            v-for="(activity, index) in activities"
            :key="index"
            :timestamp="activity.timestamp">
            {{activity.content}}
          </el-timeline-item>
        </el-timeline>
        <div v-for="item in fits" :key="item" class="block1">
          {{item}}
          </div>
          <div v-for="item in hots" :key="item" class="block2">
            {{item}}
          </div>
        </div>
      </div>
    </el-card>
    <el-card class="box-card1">
      <div slot="header" class="clearfix">
        <span>知乎</span>
        <el-button style="float: right; padding: 3px 0" type="text">操作按钮</el-button>
      </div>
      <el-header>
        <div class="title1">2,407,485</div>
        <div class="title2">最新热度</div>
        <div class="line"/>
        <div class="title3">238.1</div>
        <div class="title4">上升速度</div>
        <div class="line1"/>
        <div class="title5">1.0h</div>
        <div class="title6">在榜时长</div>
      </el-header>
      <div v-for="(item,index) in items" :key="item" class="text item">
        {{index}}--{{item}}
      </div>
      <div class="block">
        <div class="box">
          <span>节点</span>
          <span style="margin-left: 60px">排名</span>
          <span style="margin-left: 60px">热度</span>
        </div>
        <div class="box1">
          <el-timeline :reverse="reverse">
            <el-timeline-item
              v-for="(activity, index) in activities"
              :key="index"
              :timestamp="activity.timestamp">
              {{activity.content}}
            </el-timeline-item>
          </el-timeline>
          <div v-for="item in fits" :key="item" class="block1">
            {{item}}
          </div>
          <div v-for="item in hots" :key="item" class="block2">
            {{item}}
          </div>
        </div>
      </div>
    </el-card>

    <el-card class="box-card2">
      <div slot="header" class="clearfix">
        <span>b站</span>
        <el-button style="float: right; padding: 3px 0" type="text">操作按钮</el-button>
      </div>
      <el-header>
        <div class="title1">2,407,485</div>
        <div class="title2">最新热度</div>
        <div class="line"/>
        <div class="title3">238.1</div>
        <div class="title4">上升速度</div>
        <div class="line1"/>
        <div class="title5">1.0h</div>
        <div class="title6">在榜时长</div>
      </el-header>
      <div v-for="(item,index) in items" :key="item" class="text item">
        {{index}}--{{item}}
      </div>
      <div class="block">
        <div class="box">
          <span>节点</span>
          <span style="margin-left: 60px">排名</span>
          <span style="margin-left: 60px">热度</span>
        </div>
        <div class="box1">
          <el-timeline :reverse="reverse">
            <el-timeline-item
              v-for="(activity, index) in activities"
              :key="index"
              :timestamp="activity.timestamp">
              {{activity.content}}
            </el-timeline-item>
          </el-timeline>
          <div v-for="item in fits" :key="item" class="block1">
            {{item}}
          </div>
          <div v-for="item in hots" :key="item" class="block2">
            {{item}}
          </div>
        </div>
      </div>
    </el-card>
  </div>
  </div>
</template>
<script>
import axios from "axios"
export default {
  name:'hot',
  data() {
    return {
      msg: '',
      fits: {
        1:20,
        2:10,
        3:5,
      },
      hots:{
        1:325,
        2:342,
        3:3134,
      },
      items: {
        热搜标题: 'xx明星穿搭好绝',
        话题类型: "娱乐话题",
        热搜内容: '今天xx出了一个机场图，上身xx，下身xx，真的绝了',
        发布时间: "2018-01-01 11:11:11",
        发布状态: "正常发布"
      },
      activities: [{
        content: '首次上榜',
        timestamp: '2022-04-15'
      }, {
        content: '达到峰值',
        timestamp: '2022-04-13'
      }, {
        content: '达到第二峰值',
        timestamp: '2022-04-11'
      }]
    }
    },
  created() {
    axios.get('http://localhost:3200/db/test')
      .then(res => {
        this.msg = res.data
      }).catch(err => {
      console.log(err);
    })
  }
}
</script>
<style scoped>
@import url('hot.css');
</style>
