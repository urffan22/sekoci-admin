<script>
    import DashboardHeading from "../../components/dashboard/DashboardHeading.svelte";
    import Input from "../../components/forms/Input.svelte";
    import InputImages from "../../components/forms/InputImages.svelte";
    import MainTemplate from "../../templates/MainTemplate.svelte";
</script>
<MainTemplate>
    <DashboardHeading name="Tambah Slider" />
    <section class="card shadow mb-4">
        <form class="card-body">
            <div class="row">
                <div class="col-sm-6">
                    <InputImages name={"Input Gambar Slider"} />
                </div>
                <div class="col-sm-6">
                    <Input 
                        name={"Nama Slider"} 
                        type={"text"} 
                        placeholder={"Masukkan Nama Slider..."} 
                        id={"nama-slider"} 
                    />
                </div>
            </div>
            <div class="d-flex justify-content-between mt-5">
                <a href="slider" class="btn btn-outline-danger">
                    Kembali
                </a>
                <button type="submit" class="btn btn-primary">
                    Simpan
                </button>
            </div>
        </form>
    </section>
</MainTemplate>