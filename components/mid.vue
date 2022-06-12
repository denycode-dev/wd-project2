<template>
  <div class="background text-center container pb-5">
    <img
      src="https://app.sangmempelai.id/webview/template/bg/6703516c2ce92988d1f643d5ae7a1a0d.png"
      class="icons mt-4"
      alt="icons"
      loading="lazy"
    >
    <h2 class="pt-3">
      بسم الله الرحمن الرحيم
    </h2>
    <p id="Mempelai">
      Mahasuci Allah telah menciptakan manusia dengan berpasang-pasangan.
      Sungguh besar rahmat dan karunia yang diberikan-Nya kepada keluarga Kami.
      <br>
      Maka izinkan Kami mengundang sekaligus mengharapkan doa restu dari
      bapak/ibu dalam acara pernikahan putra & putri kami.
    </p>
    <div class="mt-3">
      <p class="m-0 p-0">
        Insya Allah akan di laksanakan pada:
      </p>
      <p class="m-0 p-0 font-weight-bold">
        Minggu, 17 Juli 2022
      </p>
      <vue-countdown-timer
        class="text-white mt-3 mx-n2 px-0"
        :start-time="Date()"
        :end-time="'2022-07-17 09:00:00'"
        :interval="1000"
        label-position="begin"
        :day-txt="'Hari'"
        :hour-txt="'Jam'"
        :minutes-txt="'Menit'"
        :seconds-txt="'Detik'"
        @start_callback="startCallBack('event started')"
        @end_callback="endCallBack('event ended')"
      >
        <template slot="countdown" slot-scope="scope">
          <button class="btn btn-sm bg-count-btn rounded mr-1 shadow border text-white">
            {{ scope.props.days }} {{ scope.props.dayTxt }}
          </button>
          <button class="btn btn-sm bg-count-btn rounded mr-1 shadow border text-white">
            {{ scope.props.hours }} {{ scope.props.hourTxt }}
          </button>
          <button class="btn btn-sm bg-count-btn rounded mr-1 shadow border text-white">
            {{ scope.props.minutes }} {{ scope.props.minutesTxt }}
          </button>
          <button class="btn btn-sm bg-count-btn rounded shadow border text-white">
            {{ scope.props.seconds }} {{ scope.props.secondsTxt }}
          </button>
        </template>
      </vue-countdown-timer>
    </div>
    <img
      src="https://app.sangmempelai.id/webview/template/bg/6703516c2ce92988d1f643d5ae7a1a0d.png"
      class="icons mt-4"
      alt="icons"
      loading="lazy"
    >
    <div class="row mt-4">
      <div class="col-12 col-lg-6">
        <img
          src="../static/images/profile-2.png"
          class="profile shadow mb-2"
          alt="Listiana Hikmah"
          loading="lazy"
        >
        <h4 class="text-capitalize font-weight-bold pb-0 mb-0">
          Listiana Hikmah
        </h4>
        <p class="pt-0 mt-0">
          Putri Pertama dari Bapak Yana Mustopa dan Ibu Siti Mudrikah
        </p>
      </div>
      <div class="col-12 col-lg-6">
        <img
          src="../static/images/profile-1.png"
          class="profile shadow mb-2"
          alt="Ferian Cahyana"
          loading="lazy"
        >
        <h4 class="text-capitalize font-weight-bold pb-0 mb-0">
          Ferian Cahyana
        </h4>
        <p class="pt-0 mt-0">
          Putra kedua dari Bapak Ade sopian dan Tuti Nuryanah
        </p>
      </div>
    </div>
    <img
      src="https://app.sangmempelai.id/webview/template/bg/353342e378c6a8ef955a027da32db088.png"
      class="icons mt-4"
      alt="icons"
      loading="lazy"
    >
  </div>
</template>

<script>
export default {
  name: 'MempelaiPenagantin',
  data () {
    return {
      start: '',
      end: ''
    }
  },
  methods: {
    startCallBack (x) {
      this.start = x
    },
    endCallBack (x) {
      this.end = x
    }
  }
}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;0,800;0,900;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");

.background {
  font-family: "Playfair Display", serif;
  background-image: url("https://ik.imagekit.io/denycode/asset/wd-project/85b1b13fb4ddec4abe0deb91884f9507_9BB6V2Dws.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1655007031953");
  background-position: center bottom;
  background-repeat: no-repeat;
  background-size: cover;
  background-color: #E3DBF0;
  color: #3E4448;
}

.icons {
  height: 50px;
}

.profile {
  border-radius: 50%;
  width: 100px;
  height: 100px;
  object-fit: cover;
}

.bg-count-btn {
  background: #8179A5;
  font-size: 1.10rem;
}

@media (max-width: 720px) {
  .icons {
    height: 30px;
  }
}
</style>
