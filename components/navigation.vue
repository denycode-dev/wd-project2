<template>
  <div class="navigation btn-group btn-group-sm shadow-sm">
    <button v-scroll-to="'#top'" class="btn">
      <font-awesome-icon :icon="['fa', 'home']" class="icon-fa" />
      <br>
      Home
    </button>
    <button v-scroll-to="'#Mempelai'" class="btn">
      <font-awesome-icon :icon="['fa', 'heart']" class="icon-fa" />
      <br>
      Mempelai
    </button>
    <button v-scroll-to="'#event'" class="btn">
      <font-awesome-icon :icon="['fa', 'map-marker-alt']" class="icon-fa" />
      <br>
      Acara
    </button>
    <button v-scroll-to="'#comment'" class="btn">
      <font-awesome-icon :icon="['fa', 'comment']" class="icon-fa" />
      <br>
      Ucapan
    </button>
  </div>
</template>

<script>
export default {
  name: 'NavigationBAr'
}
</script>

<style scoped>
.navigation {
    z-index: 2;
    position: fixed;
    bottom: 0;
    right: 0;
    left: 0;
    background: #E3DBF0;
    color: #3E4448;
}

button .icon-fa {
  font-size: 0.8rem !important;
  width: 18px;
}
</style>
