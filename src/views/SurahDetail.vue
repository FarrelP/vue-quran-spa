<template>
  <div class="container">
    <div class="row">
      <div class="col-md-8">
        <h1 class="mt-4 mb-4">Surat {{arrSurah.nama_latin}}</h1>
        <p class="text-muted">{{arrSurah.arti}} - {{arrSurah.jumlah_ayat}} Ayat</p>
      </div>
      <div class="col-md-4 text-right mb-4">
        <audio controls v-if="audioURL" class="mt-4">
          <source v-bind:src="audioURL" type="audio/mpeg" />
        </audio>
      </div>
    </div>

    <div class="row">
      <div class="col">
        <div class="card shadow">
          <div class="card-body">
            <h5 class="card-title">Deskripsi Surat</h5>
            <p v-html="arrSurah.deskripsi" class="card-text">{{arrSurah.deskripsi}}</p>
          </div>
        </div>
      </div>
    </div>

    <div class="row mt-4 mb-4">
      <div class="col-md-12" v-for="surah in arrSurahAyat" :key="surah.nomor">
        <CardSurahDetail :detailSurah="surah" />
      </div>
    </div>

    <div class="row">
      <div class="col fixed-bottom">
        <div class="card bg-success mb-4 card-surah-pagination">
          <div class="card-body">
            <div class="d-flex justify-content-between">
              <span v-if="typeof(arrSurah.surat_sebelumnya) == 'object'">
                <router-link :to="'/surah-detail/'+arrSurah.surat_sebelumnya.id">&#8592; {{arrSurah.surat_sebelumnya.nama_latin}}</router-link>
              </span>
              <span v-else>
                {{arrSurah.nama_latin}}
              </span>
              <span v-if="typeof(arrSurah.surat_selanjutnya) == 'object'">
                <router-link :to="'/surah-detail/'+arrSurah.surat_selanjutnya.id">{{arrSurah.surat_selanjutnya.nama_latin}} &#8594;</router-link>
              </span>
              <span v-else>
                {{arrSurah.nama_latin}}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
import CardSurahDetail from "@/components/CardSurahDetail.vue";
import axios from "axios";

export default {
  name: "SurahDetail",
  components: {
    CardSurahDetail
  },
  data() {
    return {
      arrSurah: [],
      arrSurahAyat: [],
      audioURL: ""
    };
  },
  watch: {
    '$route.params.id' : {
      handler: function() {
        this.fetchData();
        this.scrollToTop();
      } 
    }
  },
  methods: {
    fetchData() {
      axios
        .get("https://equran.id/api/surat/" + this.$route.params.id)
        .then(response => this.setSurah(response.data))
        .catch(error => console.log(error));
    },
    setSurah(data) {
      this.arrSurah = data;
      this.arrSurahAyat = data.ayat;
      this.audioURL = data.audio;
    },
    scrollToTop() {
        window.scrollTo({
          top: 0,
          behavior: 'smooth'
        });
    }
  },
  mounted() {
    this.fetchData();
  }
};
</script>

<style scoped>
</style>