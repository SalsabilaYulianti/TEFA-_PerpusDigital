<script setup>
const buku1 = ref(1);
</script>

<template>
  <div class="content">
    <div class="container-fluid">
      <div class="row">
        <div class="col-lg-12">
          <!-- <h2 class="text-center my-4">BUKU</h2> -->
          <div class="my-3">
            <input type="search" class="form-control rounded-5" placeholder="search judul buku" />
          </div>
          <!-- <div class="my-3 text-muted">menampilkan 1 dari 1</div> -->
          <div class="row">
            <div class="col-lg-2 col-5">
              <div class="card mb-3">
                <div class="card-body">
                  <img src="~/assets/cover1.jpg" class="cover" alt="cover 1" />
                </div>
                <!-- <nuxt-link to="/detail/alert"> -->
                <button type="button" class="btn btn-sm rounded-5 text-white" data-bs-toggle="modal" :data-bs-target="`#buku-${buku1}`">Lihat Detail</button>

                <!-- </nuxt-link> -->

                <div class="modal fade" :id="`buku-${buku1}`">
                  <div class="modal-dialog">
                    <div class="modal-content">
                      <div class="modal-body row d-flex justify-content-center flex-md-wrap">
                        <div class="col-3">
                          <img src="~/assets/cover1.jpg" class="cover" alt="cover 1" />
                          <div class="row"></div>
                        </div>
                        <div class="col-8">
                          <div class="row">
                            <h4>DETAIL BUKU</h4>
                          </div>
                          <div class="row">
                            <p>Judul : Dikta dan Hukum</p>
                            <p>Kategori : Buku Novel</p>
                            <p>Rak : 012</p>
                            <p>Penulis : Dhia An Farah</p>
                            <p>Penerbit : Asoka Aksara x Loveable</p>
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
.content {
  background-image: url("assets/bg.png");
  background-size: cover;
  height: 100vh;
}

/* .card-body {
  width: 100%;
  height: 20em;
  padding: 0;
} */

.cover {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: 0 30;
}

.btn {
  background: #3894bb;
  align-content: center;
  margin-left: 20%;
}

.px-4 {
  background: #3894bb;
  align-content: center;
  margin-left: 90%;
  margin-top: 14%;
}
</style>
