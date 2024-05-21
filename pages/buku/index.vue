<script setup>
const supabase = useSupabaseClient()  

const buku1 = ref([])
// const route = useRoute()
const keyword = ref('')

const getBook = async () => {
  const { data, error } = await supabase.from('Buku').select('*, kategori_buku(*)')
  if (error) throw error
  if(data) buku1.value = data
  data.forEach(book => {
    const {data} = supabase.storage.from('buku').getPublicUrl(book.cover)
    if (data) {
      book.cover = data.publicUrl
    }
  })
}

onMounted(() => {
  getBook()
})
</script>

<template>
  <div class="content">
    <div class="container-fluid">
      <div class="row">
        <div class="col-lg-12">
          <!-- <h2 class="text-center my-4">BUKU</h2> -->
          <form form @submit.prevent="getBook">
            <input v-model="keyword" type="search" class="form-control rounded-5" placeholder="search judul buku" />
          </form>
          <!-- <div class="my-3 text-muted">menampilkan 1 dari 1</div> -->
          <div class="row">
            <div v-for="(buku, i) in buku1" :key="i" class="col-lg-2">
              <div class="card mb-3">
                <div class="card-body">
                  <img :src="buku.cover" class="cover" alt="cover 1" />
                </div>
                <!-- <nuxt-link to="/detail/alert"> -->
                  <div class="text-center">
                    <button type="button" class="btn btn-sm rounded-5 text-white" data-bs-toggle="modal" :data-bs-target="`#buku-${buku1}`">Lihat Detail</button>
                  </div>

                <!-- </nuxt-link> -->

                <div class="modal fade" :id="`buku-${buku1}`">
                  <div class="modal-dialog">
                    <div class="modal-content">
                      <div class="modal-body row d-flex justify-content-center flex-md-wrap">
                        <div class="col-3">
                          <img :src="buku.cover" class="cover" alt="cover 1" />
                          <div class="row"></div>
                        </div>
                        <div class="col-8">
                          <div class="row">
                            <h4>DETAIL BUKU</h4>
                          </div>
                          <div class="row">
                            <p>Judul : {{ buku1.judul }}</p>
                            <p>Kategori : {{ buku1.kategori }}</p>
                            <p>Rak : {{ buku1.rak }}</p>
                            <p>Penulis : {{ buku1.penuklis }}</p>
                            <p>Penerbit : {{ buku1.penerbit }}</p>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="button">
          <nuxt-link to="/">
            <button type="submit" class="btn btn-sm rounded-5 px-4 text-white float-end">Kunjungan</button>
          </nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* .content {
  background-image: url("assets/bg.png");
  background-size: cover;
  height: 100vh;
} */

.card-body {
  width: 40%;
  height: 20em;
  padding: 0;
}

.cover {
  height: 100%;
  object-fit: cover;
  object-position: 0 30;
}

.btn {
  background: #3894bb;
  /* align-content: center; */
}

.px-4 {
  background: #3894bb;
  align-content: center;
  margin-left: 90%;
  margin-top: 14%;
}
</style>
