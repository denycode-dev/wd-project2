<template>
  <div id="comment" class="background text-center container pb-5">
    <img
      src="https://app.sangmempelai.id/webview/template/bg/6703516c2ce92988d1f643d5ae7a1a0d.png"
      class="icons mt-4"
      alt="icons"
    >
    <div class="">
      <h3 class="pt-1">
        Wedding Gift
      </h3>
      <p class="mx-0 mt-0 px-0 pt-0">
        Doa Restu Anda merupakan karunia yang sangat berarti bagi kami. Dan jika memberi adalah ungkapan tanda kasih Anda, Anda dapat memberi kado secara cashless.
      </p>
      <div class="card p-4 rounded text-center bg-white shadow">
        <div class="text-center">
          <img src="../static/images/logo-dana.svg" alt="dana" class="w-50">
        </div>
        <p class="m-0 p-0" style="font-size: 18px;">
          083822256003
        </p>
        <p class="m-0 p-0" style="font-size: 18px;">
          a.n Listiana Hikmah
        </p>
        <button class="btn btn-custom shadow-sm btn-sm mt-2 text-white" @click="copyText('083822256003')">
          <font-awesome-icon class="icon-fa" :icon="['fa', 'copy']" /> Salin No Rekening
        </button>
      </div>
    </div>
    <img
      src="https://app.sangmempelai.id/webview/template/bg/6703516c2ce92988d1f643d5ae7a1a0d.png"
      class="icons mt-4"
      alt="icons"
    >
    <h3 class="pt-1">
      Kirim Ucapan & Doa Restu
    </h3>
    <div v-if="alldata && alldata.length" class="p-2 rounded kartu-ucapan shadow-sm my-4">
      <div v-for="data in alldata" :key="data.id" class="card text-left p-2 custom-card mt-2 bg-white">
        <p class="p-0 m-0 font-weight-bold">
          {{ data.owner.firstName }}
        </p>
        <p class="m-0 p-0">
          {{ data.message }}
        </p>
      </div>
      <img
        src="https://app.sangmempelai.id/webview/template/bg/353342e378c6a8ef955a027da32db088.png"
        class="icons mt-4"
        alt="icons"
      >
    </div>
    <div>
      <div class="form-group text-left font-weight-bold">
        <label for="exampleInputEmail1">Nama</label>
        <input
          id="exampleInputEmail1"
          v-model="name"
          type="text"
          placeholder="masukan nama anda..."
          class="form-control shadow-sm"
          aria-describedby="emailHelp"
          @blur="createUser()"
        >
      </div>
      <div class="form-group text-left font-weight-bold">
        <label for="exampleFormControlTextarea1">Ucapan</label>
        <textarea id="exampleFormControlTextarea1" v-model="message" placeholder="tulis ucapan disini..." class="form-control shadow-sm" rows="3" />
      </div>
      <button type="submit" class="btn btn-custom shadow-sm border text-white" @click="postMessage()">
        Kirim Ucapan
      </button>
    </div>
    <img
      src="https://app.sangmempelai.id/webview/template/bg/353342e378c6a8ef955a027da32db088.png"
      class="icons mt-4"
      alt="icons"
    >
  </div>
</template>

<script>
export default {
  name: 'MempelaiPenagantin',
  data () {
    return {
      alldata: [],
      name: '',
      message: '',
      currentUserId: '',
      isSuccess: false,
      isLoad: false
    }
  },
  watch: {
    alldata (val) {
      if (val && val.length === 0) {
        setTimeout(() => {
          this.getData()
        }, 3000)
      } else {
        return null
      }
    }
  },
  beforeMount () {
    this.getData()
  },
  methods: {
    copyText (data) {
      navigator.clipboard.writeText(data)
      this.$swal.fire({
        icon: 'success',
        title: 'nomer rekening berhasil disalin',
        toast: true,
        position: 'center',
        showConfirmButton: false,
        timer: 2000,
        timerProgressBar: false
      })
    },
    getData () {
      this.$axios
        .get(
          'https://dummyapi.io/data/v1/post/628a239e2130ef8b741c8e75/comment?limit=50', {
            headers: {
              'app-id': '62236354b7ba3eea9f59dd77',
              'Content-Type': 'application/json',
              'X-Requested-With': 'XMLHttpRequest'
            }
          }
        )
        .then(function (response) {
          localStorage.setItem('allData', JSON.stringify(response.data.data))
        })
        .catch(function (error) {
          console.log(error)
        })

      setTimeout(() => {
        this.alldata = JSON.parse(localStorage.getItem('allData'))
      }, 2000)
    },
    createUser () {
      this.$axios
        .post(
          'https://dummyapi.io/data/v1/user/create', {
            firstName: this.name,
            email: Date.now().toString(36) + Math.random().toString(36).substr(2) + '@mail.com',
            lastName: 'denycode'
          }, {
            headers: {
              'app-id': '62236354b7ba3eea9f59dd77',
              'Content-Type': 'application/json',
              'X-Requested-With': 'XMLHttpRequest'
            }
          }
        )
        .then((response) => {
          // const id = response.data.id
          localStorage.setItem('currentUserId', JSON.stringify(response.data.id))
        })
        .catch(function (error) {
          console.log(error)
        })
      setTimeout(() => {
        this.currentUserId = JSON.parse(localStorage.getItem('currentUserId'))
      }, 2000)
    },
    postMessage () {
      const localId = JSON.parse(localStorage.getItem('currentUserId'))
      this.$axios
        .post(
          'https://dummyapi.io/data/v1/comment/create', {
            owner: this.currentUserId ? this.currentUserId : localId || '',
            message: this.message,
            post: '628a239e2130ef8b741c8e75'
          }, {
            headers: {
              'app-id': '62236354b7ba3eea9f59dd77',
              'Content-Type': 'application/json',
              'X-Requested-With': 'XMLHttpRequest'
            }
          }
        )
        .then(function (response) {
          //
        })
        .catch(function (error) {
          console.log(error)
        })
      setTimeout(() => {
        this.getData()
        // this.deleteUser()
      }, 3000)
      this.$swal.fire({
        icon: 'success',
        title: 'terimakasih, ucapan anda sudah terkirim',
        toast: true,
        position: 'center',
        showConfirmButton: false,
        timer: 2000,
        timerProgressBar: false
      })
      this.name = ''
      this.message = ''
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

.btn-custom {
    background-color: #8179A5;
    border-radius: 8px;
}

.btn-custom:hover {
    background-color: #7064a4;
}

.icons {
  height: 50px;
}

.rounded-custom {
  border-radius: 12px;
}

.custom-card {
    border-radius: 12px;
}

.kartu-ucapan{
    max-height: 350px;
    overflow: auto;
    background-color: rgba(180,216,183 1);
}

button .icon-fa {
  font-size: 0.8rem !important;
  width: 18px;
}

@media (max-width: 720px) {
  .icons {
    height: 30px;
  }
}
</style>
