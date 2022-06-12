<template>
  <div id="event" class="background text-center container pb-5">
    <img
      src="https://app.sangmempelai.id/webview/template/bg/6703516c2ce92988d1f643d5ae7a1a0d.png"
      class="icons mt-4"
      alt="icons"
    >
    <h3 class="pt-3">
      Rangkaian Acara
    </h3>
    <div class="row p-0 m-0">
      <div class="card bg-white rounded-custom px-4 py-2 col-12 col-lg-6">
        <h5>Akad Nikah</h5>
        <div class="text-left">
          <p class="text-capitalize">
            <font-awesome-icon class="icon-fa" :icon="['fa', 'table']" /> Minggu , 17 Juli 2022
          </p>
          <p>
            <font-awesome-icon class="icon-fa" :icon="['fa', 'clock']" /> Pukul
            09:00 WIB
          </p>
          <p class="text-capitalize">
            <font-awesome-icon
              class="icon-fa"
              :icon="['fa', 'map-marker-alt']"
            />kp.cisedong rt 02 rw 10 desa mekarjaya kecamatan cihampelas kab.bandung barat
          </p>
        </div>
      </div>
      <div
        class="
          card
          bg-white
          rounded-custom
          mt-3 mt-lg-0
          px-4
          py-2
          col-12 col-lg-6
        "
      >
        <h5>Resepsi</h5>
        <div class="text-left">
          <p class="text-capitalize">
            <font-awesome-icon class="icon-fa" :icon="['fa', 'table']" /> Minggu , 17 Juli 2022
          </p>
          <p>
            <font-awesome-icon class="icon-fa" :icon="['fa', 'clock']" /> Pukul
            10:30 WIB
          </p>
          <p class="text-capitalize">
            <font-awesome-icon
              class="icon-fa"
              :icon="['fa', 'map-marker-alt']"
            />kp.cisedong rt 02 rw 10 desa mekarjaya kecamatan cihampelas kab.bandung barat
          </p>
        </div>
      </div>
    </div>
    <div class="mt-4">
      <p>
        Merupakan kehormatan serta kebahagiaan bagi kami sekeluarga apabila
        Bapak/Ibu/Saudara/i berkenan hadir untuk memberikan doa restu kepada
        kedua mempelai.
      </p>
      <p class="font-weight-bold">
        Jazakumullah Khairan Katsiran<br>Wassalamuallaikum Warrahmatullahi
        Wabarakatuh
      </p>
      <p class="font-weight-bold mb-0 pb-2">
        Kami yang berbahagia,
      </p>
      <h5 class="font-weight-bold">
        Ferian & Listiana
      </h5>
      <p class="font-weight-bold">
        Beserta keluarga besar kedua mempelai
      </p>
    </div>
    <img
      src="https://app.sangmempelai.id/webview/template/bg/353342e378c6a8ef955a027da32db088.png"
      class="icons mt-4"
      alt="icons"
    >
    <h3 class="py-1">
      Denah Lokasi
    </h3>
    <div class="mapouter">
      <div class="gmap_canvas">
        <iframe
          id="gmap_canvas"
          height="500px"
          class="w-100"
          src="https://maps.google.com/maps?q=3CJW+554%20Toko%20Yasilir,%20Mekar%20Jaya%20Tanjung%20Jaya,%20Mekarjaya,%20Kec.%20Cihampelas,%20Kabupaten%20Bandung%20Barat,%20Jawa%20Barat%2040562&t=&z=19&ie=UTF8&iwloc=&output=embed"
          frameborder="0"
          scrolling="no"
          marginheight="0"
          marginwidth="0"
        />
        <br>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MempelaiPenagantin'
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
  color: #3e4448;
}

.icons {
  height: 50px;
}

.rounded-custom {
  border-radius: 12px;
}

.mapouter {
  position: relative;
  text-align: right;
  height: 500px;
  width: 100%;
  text-align: center;
}
.gmap_canvas {
  overflow: hidden;
  background: none !important;
  height: 500px;
  width: 100%;
}

p .icon-fa {
  font-size: 0.6rem !important;
  width: 12px;
}

@media (max-width: 720px) {
  .icons {
    height: 30px;
  }
}
</style>
