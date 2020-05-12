<template>
  <div>
    <div id="container" class="map-box"></div>
    <div class="lengend-box">
      <ul>
        <li
          v-for="(item, index) in list"
          :key="item.name"
          @click="selectHandler(index, item)"
          :class="{'active': ids.includes(item.name) }"
        >
          <img :src="item.url" alt />
          <span>{{item.name}}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Lengend",
  props: {
    list: Array
  },
  data: function() {
    return {
      ids:[]
    };
  },
  computed: {
  
  },
  methods: {
    selectHandler: function(index, item) {
      if(this.ids.includes(item.name)) return;
      this.ids.push(item.name);

      let result=[];
      this.list.forEach((listItem)=> {
        if (this.ids.includes(listItem.name)) {
          result.push(listItem);
        }
      })
      this.$emit('getSeletedData',result);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.map-box {
  height: 100vh;
  background: rebeccapurple;
}

.lengend-box {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
}

.lengend-box ul {
  display: flex;
  justify-content: center;
}

.lengend-box li {
  display: flex;
  align-items: center;
  width: 220px;
  list-style-type: none;
  margin-right: 10px;
  user-select: none;
  padding: 16px;
  background: #fff;
  color: #000;
  font-size: 14px;
  border-radius: 2px;
}

li img {
  width: 20px;
  height: 20px;
  background-size: contain;
  background-repeat: no-repeat;
  margin-right: 15px;
}

.lengend-box .active {
  margin-top: -5px;
  border-bottom: 3px solid red;
  box-shadow: 2px 2px 5px #333333;
}
</style>
