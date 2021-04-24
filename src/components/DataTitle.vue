<template>
  <div class="text-center">
    <h2 class="text-xl font-bold md:text-3xl">{{ text }}</h2>
    <div class="mt-4 mb-10 text-base md:text-2xl">
      {{ timestamp }}
    </div>
  </div>
</template>

<script>
import dayjs from 'dayjs';

export default {
  name: 'DataTitle',
  props: ['text', 'dataDate'],
  computed: {
    timestamp: function() {
      return dayjs(this.dataDate).format('D MMMM YYYY, h:mm:ss a')
    }
  }
};
</script>
