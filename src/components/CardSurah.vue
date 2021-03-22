<template>
  <div class="card mb-3">
    <div class="card-body">
      <div class="row">
        <div class="col-10">
          <h5 class="card-title surah-font">{{detailSurah.nama}}</h5>
          <p class="card-text">{{detailSurah.nama_latin}}</p>
          <p class="card-subtitle mb-2 text-muted">{{detailSurah.arti}} - {{detailSurah.jumlah_ayat}} Ayat</p>
        </div>
        <div class="col-2">
          <span class="badge badge-success">{{detailSurah.nomor}}</span>  
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardSurah",
  props: ["detailSurah"]
};
</script>

<style scoped>
</style>