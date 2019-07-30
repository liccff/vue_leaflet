<template>
<div class='mapContainer'>
   <l-map
      id="map"
      ref="map"
      :center="center"
      :min-zoom="minZoom"
      :max-zoom="maxZoom"
      :zoom="zoom"
    ></l-map>
    <div class='btnGroup'>
      <el-button type="primary" @click='drawline'>测距</el-button>
      <el-button type="primary" @click='drawploygon'>测面</el-button>
      <el-button type="primary" @click='clearAll'>清除</el-button>
    </div>
</div>
</template>

<script>
//引入资源
import maptool from "./mesure.js";
export default {
  name: 'HelloWorld',
  data () {
    return {
      center: L.latLng(34.36951139880403, 105.99746704101564),
      minZoom: 1,
      maxZoom: 18,
      zoom: 10,
      map:''
    }
  },
  mounted(){
    this.map = this.$refs.map.mapObject; //地图对象
    var VectorLayer = this.esri.tiledMapLayer({
      url: 'https://services.arcgisonline.com/arcgis/rest/services/World_Imagery/MapServer',
      opacity: 1
    });
    this.map.addLayer(VectorLayer);
  },
  methods:{
    drawline(){
      maptool.drawPolyline(this.map);
    },
    drawploygon(){
       maptool.drawPolygon(this.map);
    },
    clearAll(){
       maptool.clearplot();
    }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.mapContainer{
  width:100%;
  height:100%;
  /* background: red */
}
.btnGroup{
  position:absolute;
  z-index: 500;
  top:20px;
  left: 100px
}
</style>
