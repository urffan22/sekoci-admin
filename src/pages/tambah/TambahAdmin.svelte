<script>
    import DashboardHeading from "../../components/dashboard/DashboardHeading.svelte";
    import Input from "../../components/forms/Input.svelte";
    import MainTemplate from "../../templates/MainTemplate.svelte";
</script>
<MainTemplate>
    <DashboardHeading name={"Tambah Admin"}  />
    <section class="card shadow mb-4">
        <form class="card-body">
            <div class="row">
                <div class="col-sm-6">
                    <Input 
                        name={"Nama Admin"} 
                        placeholder={"Masukkan Nama Admin..."}
                        id={"admin-name"}
                        type={"text"}
                    />
                </div>
                <div class="col-sm-6">
                    <Input 
                        name={"Email Admin"} 
                        placeholder={"Masukkan Email Admin..."}
                        type={"email"}
                        id={"admin-email"}
                    />
                </div>
                <div class="col-sm-12">
                    <Input 
                        name={"Password Admin"} 
                        placeholder={"Masukkan Password Admin..."}
                        type={"text"}
                        id={"admin-password"}
                    />
                </div>
            </div>
            <div class="d-flex justify-content-between mt-5">
                <a href="admin" class="btn btn-outline-danger">
                    Kembali
                </a>
                <button type="submit" class="btn btn-primary">
                    Simpan
                </button>
            </div>
        </form>
    </section>
</MainTemplate>