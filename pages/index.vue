<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-lg-12">
                <h2 class="text-center my-4">ISI CATATAN KUNJUNGAN</h2>
                <form>
                    <div class="mb-3">
                        <label for="exampleInputEmail1" class="form-label">Nama</label>
                        <input type="text" class="form-control form-control-lg rounded-5">
                    </div>
                    <div class="mb-3">
                        <label for="exampleInputEmail1" class="form-label">Keanggotaan</label>
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
                    <button type="submit" class="btn btn-lg rounded-5 px-5 text-white">Kirim</button>
                </form>
            </div>
        </div>
    </div>
</template>

<style scoped>
.btn{
    background: #3894BB;
}

</style>