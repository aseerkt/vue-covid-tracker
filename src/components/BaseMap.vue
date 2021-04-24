<template>
  <div class="relative h-96">
    <div id="mapContainer" class="w-full h-full"></div>
  </div>
</template>

<script>
import mapbox from 'mapbox-gl';

export default {
  name: 'BaseMap',
  data() {
    return {
      accessToken: process.env.VUE_APP_MAPBOX_ACCESS_TOKEN,
    };
  },
  mounted() {
    mapbox.accessToken = this.accessToken;
    console.log(this.accessToken);
    new mapbox.Map({
      container: 'mapContainer',
      style: 'mapbox://styles/mapbox/streets-v11',
      center: [103.811279, 1.345399],
      zoom: 0,
      // maxBounds: [
      //   [103.6, 1.1704753],
      //   [104.1, 1.4754753],
      // ],
    });
  },
};
</script>
