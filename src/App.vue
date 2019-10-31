<template>
  <div id="app">
    <div class="head">头部</div>
    <MescrollVue>
      <div class="cont">
        <ul>
          <li v-for="(v,i) in list" :key="i">{{v.name}}</li>
        </ul>
      </div>
    </MescrollVue>
    <div class="foot">尾部</div>
  </div>
</template>

<script>
import axios from 'axios';
import MescrollVue from "mescroll.js/mescroll.vue";
export default {
  name: "app",
  components: {
    MescrollVue
  },
  data() {
    return {
      list: [
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" },
        { name: "今天是个好日子" }
      ],
      mescroll: null, // mescroll实例对象
      mescrollDown: {
        callback: this.upCallback,
        page: {
          num: 0,
          size: 5
        },
        htmlNodata: '<p class="upwarp-nodata">-- END --</p>',
        noMoreSize: 5,
        toTop: {
          //回到顶部按钮
          src: "./static/mescroll/mescroll-totop.png", //图片路径,默认null,支持网络图
          offset: 1000 //列表滚动1000px才显示回到顶部按钮
        }
      },
      mescrollUp: {
        callback: this.upCallback
      }
    };
  },
  methods: {
    upCallback(page, mescrill) {
      axios.get()
    }
  }
};
</script>

<style lang="scss">
html,
body {
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
}
#app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
}
.head,
.foot {
  width: 100%;
  height: 60px;
  border: 1px solid;
  text-align: center;
  line-height: 60px;
  font-size: 20px;
  font-weight: bold;
  box-sizing: border-box;
}
.cont {
  flex: 1;
  overflow: auto;
}
ul,
li {
  list-style: none;
  margin: 0;
  padding: 0;
}
li {
  width: 100%;
  height: 40px;
  text-align: center;
  line-height: 40px;
  box-sizing: border-box;
  // border: 1px solid red;
}
</style>