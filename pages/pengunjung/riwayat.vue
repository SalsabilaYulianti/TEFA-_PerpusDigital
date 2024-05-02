<template>
  <div class="container-fluid">
    <div class="content">
      <div class="row">
        <div class="col-lg-12">
          <h2 class="text-center my-4">RIWAYAT KUNJUNGAN</h2>
          <div class="my-3 text-munted layar">
              15 dari 15 kunjungan
            <table class="table border">
              <thead>
              <tr>
                <td >No</td>
                <td>Tanggal</td>
                <td>Waktu</td>
                <td>Nama</td>
                <td>Keanggotaan</td>
                <td>Kelas</td>
                <td>Keperluan</td>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>1.</td>
                <td>14 Maret 2024</td>
                <td>10.34</td>
                <td>Ananta</td>
                <td>Siswa</td>
                <td>XI PPLG 3</td>
                <td>Membaca</td>
              </tr>
            </tbody>
          </table>
          <nuxt-link to="/buku/">
            <button type="submit" class="btn btn-lg rounded-5 px-4 text-white float-end">Cari buku</button>
          </nuxt-link>
          <nuxt-link to="/">
            <button type="submit" class="btn btn-lg rounded-5 px-4 text-white float-end">Kembali</button>
          </nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inknut+Antiqua:wght@300;400;500;600;700;800;900&family=Inria+Serif:ital,wght@0,300;0,400;0,700;1,300;1,400;1,700&family=Inter:wght@100..900&display=swap');
.text-center{
    font-family: "Inria Serif", serif;
    font-size: 35px;
    font-weight: 500;
    font-style: normal;
}
.content {
    background-image: url("assets/bg.png");
    background-size: cover;
    height: 100vh;
    }

.btn {
    background: #3894bb;
    }

/* table {
    background-color: #fdfdfdda;
  } */

.layar{
  background-color: #fdfdfddb;
  height: 100%;
}
td{
  border: 1px solid;
}
</style>