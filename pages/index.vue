<script setup>
const supabase = useSupabaseClient()
const members = ref ([])
const objectives = ref ([])
const form = ref ({
    nama: "",
    keanggotaan: "",
    tingkat: "",
    jurusan: "",
    kelas: "",
    keperluan: "",
})

const kirimData = async () => {
    const { error } = await supabase.from('Pengunjung').insert([form.value])
    console.log(error)
    if(!error) navigateTo('/pengunjung/riwayat')
}

const getKeanggotaan = async () => {
    const { data, error } = await supabase.from('Keanggotaan').select('*')
    if(data) members.value = data
}

const getKeperluan = async () => {
    const { data, error } = await supabase.from('Keperluan').select('*')
    if(data) objectives.value = data
}

onMounted(() => {
    getKeanggotaan()
    getKeperluan()
})

</script>

<template>
    <div class="content">
    <div class="container-fluid mb-5">
            <div class="row d-flex justify-content-center">
            <div class="col-lg-12 ">
                <strong><h2 class="text-center my-4 fw-bold font-inter">ISI CATATAN KUNJUNGAN</h2></strong>
                <!-- <div class="offset-lg-2 col-lg-8"> -->
            </div>
                <form @submit.prevent="kirimData" class="rounded mb-5">
                    <div class="mb-3">
                    <label for="nama">Nama</label>
                    <input v-model="form.nama" type="text" class="form-control form-control-lg rounded-5" autocomplete="off" />
                    </div>
                    <div class="mb-3">
                    <label for="exampleInputEmail1" class="form-label" autocomplete="off">Keanggotaan</label>
                    <select v-model="form.keanggotaan" class="form-control form-control-lg form-select rounded-5">
                        <option value=""></option>
                        <option v-for="(member, i) in members" :key="i" :value="member.id">{{ member.nama }}</option>
                    </select>
                    </div>
                    <div v-if="form.keanggotaan == '2'" class="mb-3">
                    <div class="row">
                        <label for="exampleInputEmail1" class="form-label" autocomplete="off">Kelas Lengkap</label>
                        <div class="col-md-4">
                        <select v-model="form.tingkat" class="form-control form-control-lg form-select tounded-5 mb-2">
                            <option value="">Tingkat</option>
                            <option value="X">X</option>
                            <option value="XI">XI</option>
                            <option value="XII">XII</option>
                        </select>
                        </div>
                        <div class="col-md-4">
                        <select v-model="form.jurusan" class="form-control form-control-lg form-select tounded-5 mb-2">
                            <option value="">Jurusan</option>
                            <option value="PPLG">PPLG</option>
                            <option value="TJKT">TJKT</option>
                            <option value="TBSM">TBSM</option>
                            <option value="DKV">DKV</option>
                            <option value="TOI">TOI</option>
                        </select>
                        </div>
                        <div class="col-md-4">
                        <select v-model="form.kelas" class="form-control form-control-lg form-select tounded-5 mb-2">
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
                    <select v-model="form.keperluan" class="form-control form-control-lg form-select rounded-5">
                        <option value=""></option>
                        <option v-for="(item, i) in objectives" :key="i" :value="item.id">{{ item.nama }}</option>
                    </select>
                    </div>
                    <button type="submit" class="btn btn-sm rounded-2 px-4 text-white mb- 5">Kirim</button>
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

    /* .content {
    background-image: url("assets/bg.png");
    background-size: cover;
    height: 100vh;
    } */

    .form-control {
    background: #d9d9d9;
    }

    form {
    background-color: #fdfdfdda;
    width: 30rem;
    }
</style>