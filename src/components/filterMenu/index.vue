<template>
  <div>
    <div id="container" class="map-box"></div>
    <div class="lengend-box">
      <ul>
        <li
          v-for="(item, index) in data"
          :key="item.name"
          @click="selectHandler(index, item)"
          :class="{'active': item.isSelected }"
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
    data: Array
  },
  mounted: function() {
    console.log(this.data, "====data====");
  },
  methods: {
    selectHandler: function(index, item) {
      item.isSelected = !item.isSelected;
      this.$emit('getSeletedData', item);
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
}

li img {
  width: 20px;
  height: 20px;
  background-size: contain;
  background-repeat: no-repeat;
  margin-right: 15px;
}

.lengend-box .active {
  border-bottom: 3px solid red;
}
</style>
