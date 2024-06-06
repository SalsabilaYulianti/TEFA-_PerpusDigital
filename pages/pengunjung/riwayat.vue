<script setup>
const supabase = useSupabaseClient()
const visitors = ref ([])

const getPengunjung = async () => {
  const { data, error } = await supabase.from("Pengunjung").select(`*, Keanggotaan(*), Keperluan(*)`).order('id', { ascending: false })
  if(data) visitors.value = data
}
onMounted(() => getPengunjung())

</script>

<template>
  <div class="content">
    <div class="container-fluid">
      <div class="row">
        <div class="col-lg-12">
          <strong><h2 class="text-center my-4">RIWAYAT KUNJUNGAN</h2></strong>
          <div class="my-3 text-munted layar table-responsive">
            {{ visitors.length }} dari {{ visitors.length }} kunjungan
            <table class="table border">
              <thead>
                <tr>
                  <td>No</td>
                  <td>Tanggal</td>
                  <td>Waktu</td>
                  <td>Nama</td>
                  <td>Keanggotaan</td>
                  <td>Kelas</td>
                  <td>Keperluan</td>
                </tr>
              </thead>
              <tbody>
                <tr v-for="(visitor, i) in visitors" :key="i">
                  <td>{{ i + 1 }}</td>
                  <td>{{ visitor.tanggal }}</td>
                  <td>{{ visitor.waktu }}</td>
                  <td>{{ visitor.nama }}</td>
                  <td>{{ visitor.Keanggotaan.nama }}</td>
                  <td>{{ visitor.tingkat }} {{ visitor.jurusan }} {{ visitor.kelas }}</td>
                  <td>{{ visitor.Keperluan.nama }}</td>
                </tr>
              </tbody>
            </table>
            <nuxt-link to="/buku/">
              <button type="submit" class="btn btn-sm rounded-2 px-4 text-white float-end">Cari buku</button>
            </nuxt-link>
            <nuxt-link to="/">
              <button type="submit" class="btn btn-sm rounded-2 px-4 text-white float-end">Kembali</button>
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Inknut+Antiqua:wght@300;400;500;600;700;800;900&family=Inria+Serif:ital,wght@0,300;0,400;0,700;1,300;1,400;1,700&family=Inter:wght@100..900&display=swap");
.text-center {
  font-family: "Inria Serif", serif;
  font-size: 35px;
  font-weight: 500;
  font-style: normal;
}

.btn {
  background: #3894bb;
  margin-left: auto;
}

/* table {
    background-color: #fdfdfdda;
  } */

.layar {
  background-color: #fdfdfddb;
  height: 100%;
}
td {
  border: 1px solid;
}
</style>