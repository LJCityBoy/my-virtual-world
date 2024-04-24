

<template>
  <div id="cesium-container"></div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue'
import * as Cesium from 'cesium'

onMounted(() => {
  //配置token
  Cesium.Ion.defaultAccessToken = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJqdGkiOiJhYjQ4Mzk5NS03OGYzLTQ1NGItODM3ZC1lNTI4NTUyZjllYWMiLCJpZCI6MTEyNzYsImlhdCI6MTcxMzk3MzgxMH0.-YBx86oMJLA1SKl1yvWVetk2KsQw65N9Thi048Xly0E'
  //初始化
  const viewer = new Cesium.Viewer('cesium-container', { terrain: Cesium.Terrain.fromWorldTerrain() })

  viewer.camera.flyTo({
    destination: Cesium.Cartesian3.fromDegrees(-122.4175, 37.655, 400),
    orientation: {
      heading: Cesium.Math.toRadians(0.0),
      pitch: Cesium.Math.toRadians(-15.0),
    }
  })
})


</script>

<style scoped>
.cesium-container {
  height: 100%;
  width: 100%;
}
</style>
