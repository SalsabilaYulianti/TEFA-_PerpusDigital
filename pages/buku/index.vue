<template>
  <div class="container-fluid">
    <div class="content">
      <div class="row">
        <div class="col-lg-12">
          <!-- <h2 class="text-center my-4">BUKU</h2> -->
          <div class="my-3">
            <input type="search" class="form-control rounded-5" placeholder="search judul buku">
          </div>
          <!-- <div class="my-3 text-muted">menampilkan 1 dari 1</div> -->
          <div class="row">
            <div class="col-lg-2">
              <div class="card mb-3">
                <div class="card-body">
                  <img src="~/assets/cover1.jpg" class="cover" alt="cover 1">
                </div>
                <nuxt-link to="/detail/alert">
                <button type="submit" class="btn btn-lg rounded-5 text-white d-flex">Lihat Detail</button>
                </nuxt-link>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.content{
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
    }
</style>
