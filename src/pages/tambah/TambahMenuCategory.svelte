<script>
    import DashboardHeading from "../../components/dashboard/DashboardHeading.svelte";
    import Input from "../../components/forms/Input.svelte";
    import InputImages from "../../components/forms/InputImages.svelte";    
    import MainTemplate from "../../templates/MainTemplate.svelte";
</script>

<MainTemplate>    
    <DashboardHeading name={"Tambah Menu Category"} />
    <section class="card shadow mb-4">
        <form class="card-body">
            <div class="row">
                <div class="col-sm-12">    
                    <Input 
                        name={"Nama Kategori"} 
                        id={"nama-menu"} 
                        type={"text"} 
                        placeholder={"Input Nama Menu.."} 
                    />
                    <InputImages name={"Gambar Kategori"} />                    
                </div>                
            </div>
            <div class="d-flex justify-content-between mt-5">
                <a href="menu-kategori" class="btn btn-outline-danger">
                    Kembali
                </a>
                <button type="submit" class="btn btn-primary">
                    Simpan
                </button>
            </div>
        </form>
    </section>
</MainTemplate>