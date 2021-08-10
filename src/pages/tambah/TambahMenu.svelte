<script>
    import DashboardHeading from "../../components/dashboard/DashboardHeading.svelte";
    import Input from "../../components/forms/Input.svelte";
    import InputDropdowns from "../../components/forms/InputDropdowns.svelte";
import InputImages from "../../components/forms/InputImages.svelte";
    import RichText from "../../components/forms/RichText.svelte";
    import MainTemplate from "../../templates/MainTemplate.svelte";
</script>
<!-- 
    contoh penggunaan dropdown
    <InputDropdowns 
        name={"Tambah Kategori"} 
        category_id={"tambah-kategori"}
        options = {[
            { name: "Makanan" },
            { name: "Minuman" }                           
        ]}
    />
 -->
<MainTemplate>
    <DashboardHeading name={"Tambah Menu"} />
    <section class="card shadow mb-4">
        <form class="card-body">
            <div class="row">
                <div class="col-sm-6">
                    <InputDropdowns 
                        name={"Tambah Kategori"} 
                        category_id={"tambah-kategori"}
                        options = {[
                            { name: "Makanan", value: "makanan" },
                            { name: "Minuman", value: "minuman" },
                            { name: "Desert", value: "desert" }
                        ]}
                    />
                </div>
                <div class="col-sm-6">
                    <Input name={"Nama Menu"} id={"nama-menu"} type={"text"} placeholder={"Input Nama Menu.."} />
                </div>
                <div class="col-sm-6">
                    <Input name={"Subtitle Menu"} id={"subtitle-menu"} type={"text"} placeholder={"Input Subtitle Menu..."} />
                </div>
                <div class="col-sm-6">
                    <Input name={"Harga Menu"} id={"price-menu"} type={"number"} placeholder={"Input Harga Menu..."} />
                </div>
                <div class="col-sm-6">
                    <InputImages name={"Gambar Menu"} />
                </div>
                <div class="col-sm-6">
                    <RichText label={"Deskripsi"} id={"deskripsi-menu"} />
                </div>
            </div>
            <div class="d-flex justify-content-between mt-5">
                <a href="menu" class="btn btn-outline-danger">
                    Kembali
                </a>
                <button type="submit" class="btn btn-primary">
                    Simpan
                </button>
            </div>
        </form>
    </section>
</MainTemplate>