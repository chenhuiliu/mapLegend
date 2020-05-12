<template>
  <div id="app">
    <filterMenu :list="list" v-on:getSeletedData='getData'/>
  </div>
</template>

<script>
import filterMenu from "./components/filterMenu/index";

export default {
  name: "App",
  components: {
    filterMenu
  },
  data: function() {
    return {
      list: [
        {
          name: "奥迪",
          url: "http://qa5vj5o3r.bkt.clouddn.com/%E5%A5%A5%E8%BF%AA%20%284%29.png",
          // isSelected: false
        },
        {
          name: "一汽大众",
          url: "http://qa5vj5o3r.bkt.clouddn.com/%E5%A4%A7%E4%BC%97.png",
          // isSelected: false
        },
        {
          name: "充电桩",
          url: "http://qa5vj5o3r.bkt.clouddn.com/%E5%A5%A5%E8%BF%AA%20%284%29.png",
          // isSelected: false
        },
        {
          name: "特斯拉",
          url: "http://qa5vj5o3r.bkt.clouddn.com/%E5%A5%A5%E8%BF%AA%20%284%29.png",
          // isSelected: false
        },
        {
          name: "奥迪2",
          url: "http://qa5vj5o3r.bkt.clouddn.com/%E5%A5%A5%E8%BF%AA%20%284%29.png",
          // isSelected: false
        },
        {
          name: "奥迪3",
          url: "http://qa5vj5o3r.bkt.clouddn.com/%E5%A5%A5%E8%BF%AA%20%284%29.png",
          // isSelected: false
        }
      ]
    }
  },
  methods: {
    getData: function(a) {
      console.log(11111111111,a);
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
