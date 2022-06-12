<template>
  <div class="bg pb-5">
    <div class="filter">
      <div class="contain">
        <Transition>
          <img src="../static/images/1645981694862.png" alt="aldi annisa logo" class="logo">
        </Transition>
        <h4>Undangan Pernikahan Digital<br>Ferian & Listiana</h4>
        <Transition>
          <div class="mt-4">
            <p>Kpd. Bpk/Ibu/Saudara/i</p>
            <p class="text-capitalize">
              {{ rename($route.params.slug) }}
            </p>
            <nuxt-link to="/" class="btn custom-btn px-4 font-weight-bold text-white shadow-sm" role="button">
              Buka Undangan
            </nuxt-link>
          </div>
        </Transition>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    rename (param) {
      if (param) {
        return param.split('-').join(' ')
      }
    }
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
.bg {
  background-image: url('https://ik.imagekit.io/denycode/asset/wd-project/85b1b13fb4ddec4abe0deb91884f9507_9BB6V2Dws.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1655007031953');
  width: 100vw !important;
  height: 100vh;
  background-color: #E3DBF0;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
.filter {
  background: rgba(0, 0, 0, 0.5);
  position: absolute;
  z-index: 1;
  height: 100vh;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
}

.contain {
  color: #d2d1d1;
  text-align: center;
  z-index: 2;
  font-family: 'Playfair Display', serif;
  margin-top: 10%;
}

.profile {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  object-fit: cover;
}

.logo {
  max-height: 250px;
  -webkit-filter: drop-shadow(5px 5px 5px #222);
  filter: drop-shadow(5px 5px 5px #222);
}

.custom-btn{
  border-radius: 10px;
  background: #8179A5;
  color: white;
}

.custom-btn:hover{
  border-radius: 10px;
  background: #7064a4;
}
@media(max-width:720px){
  .contain {
  margin-top: 25%;
}
}
</style>
