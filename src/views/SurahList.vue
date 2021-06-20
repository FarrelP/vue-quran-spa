<template>
  <div class="container">
    <h1 class="mt-4 mb-4">Daftar Surat</h1>

    <div class="row mb-4">
        <div class="col-lg-4 col-md-6" v-for="surah in arrSurah" :key="surah.nomor">
          <CardSurah :detailSurah="surah" />
        </div>
      </div>
  </div>
</template>

<script>
import CardSurah from "@/components/CardSurah.vue";
import axios from "axios";

export default {
  name: "SurahList",
  components: {
    CardSurah
  },
  data() {
    return {
      arrSurah: [],
    };
  },
  methods: {
    setSurah(data) {
      this.arrSurah = data;
    }
  },
  mounted() {
    axios
      .get("https://equran.id/api/surat")
      .then(response => this.setSurah(response.data))
      .catch(error => console.log(error));
  }
};
</script>

<style scoped>
</style>