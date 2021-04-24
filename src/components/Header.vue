<template>
  <header class="p-4 mb-10 text-center text-white bg-blue-800">
    <router-link to="/">
      <div class="mb-3 text-3xl font-bold uppercase md:text-4xl">
        <i class="fa fa-viruses"></i> Covid-19 Tracker
      </div>
    </router-link>
    <p>
      API by
      <a class="text-blue-300" target="_blank" href="https://covid19api.com"
        >covid19api.com</a
      >
    </p>
    <nav class="py-3 rounded shadow-md">
      <ul class="flex justify-center mt-3 text-sm align-middle">
        <li>
          <router-link class="p-2 mx-2 font-semibold uppercase opacity-70 hover:opacity-100" to='/'>
            Home
          </router-link>
        </li>
        <li>
          <router-link class="p-2 mx-2 font-semibold uppercase opacity-70 hover:opacity-100" to='/about'>
            About
          </router-link>
        </li>
        <li>
          <router-link class="p-2 mx-2 font-semibold uppercase opacity-70 hover:opacity-100" to='/map'>
            Map
          </router-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
};
</script>
