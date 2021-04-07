<template>
  <div class="card mb-3 shadow">
    <div class="card-body">
      <div class="row">
        <div class="col">
          <span class="badge badge-success">{{detailSurah.nomor}}</span>  
          <p class="surah-font text-right mt-3">{{detailSurah.ar}}</p>
          <p class="mt-3" v-html="detailSurah.tr">{{detailSurah.tr}}</p>
          <p class="text-muted">{{detailSurah.idn}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardSurahDetail",
  props: ["detailSurah"]
};
</script>

<style scoped>
</style>