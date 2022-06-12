<template>
  <div class="overflow-hidden" style="background: #E3DBF0;">
    <top class="mb-3" />
    <mid class="mb-3" />
    <navigation />
    <event class="mb-3" />
    <ucapan class="mb-3" />
    <b-modal v-model="modalShow" hide-footer centered hide-header>
      <div class="text-center">
        <img src="https://ik.imagekit.io/denycode/asset/wd-project/pngtree-protokol-kesehatan-5m-covid-19-masker-jaga-jarak-cuci-tangan-png-image_4378110_6Rpyjwwcu.png?ik-sdk-version=javascript-1.4.3&updatedAt=1655008898747" class="w-100" alt="protokol">
        <button class="btn btn-sm rounded text-dark mt-3 shadow-sm font-weight-bold border" style="background: #8179A5;" @click="modalShow = false">
          tutup
        </button>
      </div>
    </b-modal>
    <div class="audio-control">
      <audio
        id="audio"
        ref="audio"
        src="https://sndup.net/dxdb/d"
        preload
        loop
        autoplay
        controls
      />
    </div>
    <!-- <audio autoplay="true" class="d-none" src="https://cdn.sndup.net/jf6q/music%20(1).mp3?token=qaWL8FixQsmLGjLttPWDBovSy7mB17Mo_pRVh-2S4DQ&token_path=%2Fjf6q%2F&expires=1653319022" /> -->
  </div>
</template>

<script>
import top from '~/components/top.vue'
import mid from '~/components/mid.vue'
import navigation from '~/components/navigation.vue'
import event from '~/components/event.vue'
import ucapan from '~/components/ucapan.vue'
// const notificationSound = require('../static/sound/music.mp3')
export default {
  name: 'IniIndex',
  components: {
    top,
    mid,
    navigation,
    event,
    ucapan
  },
  data () {
    return {
      modalShow: true
      // notificationSound
    }
  },
  created () {
    this.showModal()
  },
  methods: {
    showModal () {
      this.modalShow = true
    }
    // playAudio () {
    //   const audio = new Audio(this.notificationSound)
    //   setTimeout(() => {
    //     audio.play()
    //   }, 4000)
    // }
  }
}
</script>
<style scoped>
.audio-control {
  position: fixed;
  z-index: 99999;
  bottom: 8%;
  right: 10vw;
}
audio {
    max-height: 30px;
    width: 100px;
}

audio::-webkit-media-controls-timeline-container,

audio::-webkit-media-controls-current-time-display,

audio::-webkit-media-controls-time-remaining-display,

audio::-webkit-media-controls-timeline,

audio::-webkit-media-controls-volume-slider-container,

audio::-webkit-media-controls-volume-slider,

audio::-webkit-media-controls-seek-back-button,

audio::-webkit-media-controls-seek-forward-button,

audio::-webkit-media-controls-fullscreen-button,

audio::-webkit-media-controls-rewind-button,

audio::-webkit-media-controls-return-to-realtime-button,

audio::-webkit-media-controls-toggle-closed-captions-button {
  display: none
}

audio::-webkit-media-controls-panel {
  background: #E3DBF0;
}

</style>
