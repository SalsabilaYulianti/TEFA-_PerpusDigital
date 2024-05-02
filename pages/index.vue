<template>
    <div class="container-fluid">
        <div class="content">
            <div class="row d-flex justify-content-center">
            <div class="col-lg-12 ">
                <h2 class="text-center my-4 fw-bold font-inter">ISI CATATAN KUNJUNGAN</h2>
                <!-- <div class="offset-lg-2 col-lg-8"> -->
            </div>
                <form class="rounded">
                    <div class="mb-3">
                    <label for="nama">Nama</label>
                    <input type="text" class="form-control form-control-lg rounded-5" autocomplete="off" />
                    </div>
                    <div class="mb-3">
                    <label for="exampleInputEmail1" class="form-label" autocomplete="off">Keanggotaan</label>
                    <select class="form-control form-control-lg form-select rounded-5">
                        <option value=""></option>
                        <option value="Siswa">Siswa</option>
                        <option value="Guru">Guru</option>
                        <option value="Staf">Staf</option>
                        <option value="Umum">Umum</option>
                    </select>
                    </div>
                    <div class="mb-3">
                    <div class="row">
                        <div class="col-md-4">
                        <select class="form-control form-control-lg form-select tounded-5 mb-2">
                            <option value="">Tingkat</option>
                            <option value="X">X</option>
                            <option value="XI">XI</option>
                            <option value="XII">XII</option>
                        </select>
                        </div>
                        <div class="col-md-4">
                        <select class="form-control form-control-lg form-select tounded-5 mb-2">
                            <option value="">Jurusan</option>
                            <option value="X">PPLG</option>
                            <option value="XI">TJKT</option>
                            <option value="XII">TBSM</option>
                            <option value="XII">DKV</option>
                            <option value="XII">TOI</option>
                        </select>
                        </div>
                        <div class="col-md-4">
                        <select class="form-control form-control-lg form-select tounded-5 mb-2">
                            <option value="">Kelas</option>
                            <option value="1">1</option>
                            <option value="2">2</option>
                            <option value="3">3</option>
                            <option value="4">4</option>
                        </select>
                        </div>
                    </div>
                    </div>
                    <div class="mb-3">
                    <label for="exampleInputEmail1" class="form-label">Keperluan</label>
                    <select class="form-control form-control-lg form-select rounded-5">
                        <option value=""></option>
                        <option value="baca">Baca Buku</option>
                        <option value="pinjam">Meminjam Buku</option>
                        <option value="kembalikan">Kembalikan Buku</option>
                    </select>
                    </div>
                    <nuxt-link to="pengunjung/riwayat">
                    <button type="submit" class="btn btn-lg rounded-5 px-4 text-white ">Kirim</button>
                    </nuxt-link>
                </form>
                </div>
            </div>
        <!-- </div> -->
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

    .btn {
    background: #3894bb;
    margin-left: 75%;
    }

    .content {
    background-image: url("assets/bg.png");
    background-size: cover;
    height: 100vh;
    }

    .form-control {
    background: #d9d9d9;
    }

    form {
    background-color: #fdfdfdda;
    width: 30rem;
    }
</style>
