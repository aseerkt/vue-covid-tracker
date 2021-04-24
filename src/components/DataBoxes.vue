<template>
  <div class="grid gap-4 md:grid-cols-3">
    <!-- Box 1 -->
    <div class="p-10 text-center bg-blue-200 rounded shadow-md">
      <h3 class="mb-4 text-3xl font-bold text-blue-900">Confirmed</h3>
      <div class="mb-4 text-2xl">
        <span class="font-bold">New:</span>
        {{ numberWithCommas(stats.NewConfirmed) }}
      </div>
      <div class="mb-4 text-2xl">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalConfirmed) }}
      </div>
    </div>

    <!-- Box 2 -->
    <div class="p-10 text-center bg-green-200 rounded shadow-md">
      <h3 class="mb-4 text-3xl font-bold text-green-900">Recovered</h3>
      <div class="mb-4 text-2xl">
        <span class="font-bold">New:</span>
        {{ numberWithCommas(stats.NewRecovered) }}
      </div>
      <div class="mb-4 text-2xl">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalRecovered) }}
      </div>
    </div>

    <!-- Box 3 -->
    <div class="p-10 text-center bg-red-200 rounded shadow-md">
      <h3 class="mb-4 text-3xl font-bold text-red-900">Deaths</h3>
      <div class="mb-4 text-2xl">
        <span class="font-bold">New:</span>
        {{ numberWithCommas(stats.NewDeaths) }}
      </div>
      <div class="mb-4 text-2xl">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalDeaths) }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DataBoxes',
  props: ['stats'],
  methods: {
    numberWithCommas(x) {
      return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
    },
  },
};
</script>
