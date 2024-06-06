<script setup>
const supabase = useSupabaseClient()  

const buku1 = ref([])
// const route = useRoute()
const keyword = ref('')

const getBook = async () => {
  const { data, error } = await supabase.from('Buku').select('*, kategori_buku(*)')
  .ilike('judul',`%${keyword.value}%`)
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
        
          <!-- <h2 class="text-center my-4">BUKU</h2> -->
          <form form @submit.prevent="getBook" class="p-5">
            <input v-model="keyword" type="search" class="form-control rounded-5" placeholder="search judul buku" />
          </form>
          
          <!-- <div class="my-3 text-muted">menampilkan 1 dari 1</div> -->
          <div class="row justify-content-center">
            <div v-for="(buku, i) in buku1" :key="i" class="col-sm m-2 d-flex justify-content-center">
              
              <div class="card mb-3">
                <div class="card-body p-0">
                  <img :src="buku.cover" class="cover" alt="cover 1" />
                </div>
                <!-- <nuxt-link to="/detail/alert"> -->
                  <div class="text-center">
                    <button type="button" class="btn btn-sm rounded-2 text-white mb-3" data-bs-toggle="modal" :data-bs-target="`#buku-${buku.id}`">Lihat Detail</button>
                  </div>

                <!-- </nuxt-link> -->

                <div class="modal fade" :id="`buku-${buku.id}`">
                  <div class="modal-dialog modal-lg">
                    <div class="modal-content">
                      <div class="modal-body row d-flex justify-content-center">
                        <div class="col-lg-4 col-md-5 col-sm-6 col-7">
                          <img :src="buku.cover" class="cover" alt="cover 1" />
                          <!-- <div class="row"></div> -->
                        </div>
                        <div class="col-lg-8 col-md-7 col-sm-6 col-6">
                          <div class="row ">
                            <h4>DETAIL BUKU</h4>
                          </div>
                          <div class="row ">
                            <p>Judul : {{ buku.judul }}</p>
                            <p>Kategori : {{  buku.kategori }}</p>
                            <p>Rak : {{ buku.rak }}</p>
                            <p>Penulis : {{ buku.penulis }}</p>
                            <p>Penerbit : {{ buku.penerbit }}</p>
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
            <button type="submit" class="btn btn-sm rounded-2 text-white float-end">Kunjungan</button>
          </nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* @media only screen and(max-width: 960px){
  .row{
    margin-left: auto;
  }
} */
/* .content {
  background-image: url("assets/bg.png");
  background-size: cover;
  height: 100vh;
} */

.card {
  height: 19em;
  width: 200px;
}

.cover {
  width: 180px;
  height: 14rem;
  margin: 10px;
  object-fit: cover;
  object-position: 0 30;
}

.btn {
  background: #3894bb;

  /* align-content: center; */
}

/* .px-4 {
  background: #3894bb;
  align-content: center;
  margin-left: 90%;
  margin-top: 14%;
} */
</style>
