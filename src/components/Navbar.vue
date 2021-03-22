<template>
  <nav class="navbar navbar-expand-lg navbar-light shadow-sm p-2 mb-2 rounded">
    <div class="container">
      <img src="../assets/images/quran-icon.png" alt="Quran Icon" height="35">
      <a class="navbar-brand" href="#">Baca Quran Web App</a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <router-link to="/" class="nav-link">Beranda</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/surah-list" class="nav-link">Daftar Surat</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/about" class="nav-link">Tentang</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar"
};
</script>

<style scoped>
</style>