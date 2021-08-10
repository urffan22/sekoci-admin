<script>
    import DashboardHeading from "../../components/dashboard/DashboardHeading.svelte";
    import Input from "../../components/forms/Input.svelte";
    import InputImages from "../../components/forms/InputImages.svelte";
    import MainTemplate from "../../templates/MainTemplate.svelte";
</script>

<MainTemplate>
    <DashboardHeading name={"Tambah Data Onboarding"} />
    <section class="card shadow mb-4">
        <form class="card-body">
            <div class="row">
                <div class="col-sm-6">
                    <Input name={"Urutan"} type={"number"} id={"urutan"} />
                </div>
                <div class="col-sm-6">
                    <Input name={"Judul"} type={"text"} id={"judul"} />
                </div>                
            </div>
            <div class="row">
                <div class="col-sm-6">
                    <InputImages name={"onboarding"} />
                </div>
                <div class="col-sm-6">
                    <Input name={"Keterangan"} type={"text"} id={"keterangan"} />
                </div>
            </div>
            <div class="d-flex justify-content-between mt-5">
                <a href="onboarding" class="btn btn-outline-danger">
                    Kembali
                </a>
                <button type="submit" class="btn btn-primary">
                    Simpan
                </button>
            </div>
        </form>
    </section>
</MainTemplate>