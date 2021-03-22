<template>
  <div class="container">
    <h1 class="mt-4 mb-4">Daftar Surat</h1>

    <!-- <div class="row mt-3">
      <div class="col">
        <div class="input-group mb-3">
          <input
            v-model="valSearch"
            type="text"
            class="form-control"
            placeholder="Cari Surat"
            aria-label="Cari"
            aria-describedby="basic-addon2"
            @keyup="searchSurah"
          />
          <div class="input-group-append">
            <span class="input-group-text" id="basic-addon2">
              <b-icon-search></b-icon-search>
            </span>
          </div>
        </div>
      </div>
    </div> -->

    <div class="row mb-4">
        <div class="col-md-4" v-for="surah in arrSurah" :key="surah.nomor">
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
      valSearch: '',
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