<script>
    import DashboardHeading from "../../components/dashboard/DashboardHeading.svelte";
import Input from "../../components/forms/Input.svelte";
import InputDropdowns from "../../components/forms/InputDropdowns.svelte";
import InputImages from "../../components/forms/InputImages.svelte";
    import MainTemplate from "../../templates/MainTemplate.svelte";
</script>
<MainTemplate>
    <DashboardHeading name={"Tambah Konsumen"} />
    <section class="card shadow mb-4">
        <form class="card-body">
            <div class="row">
                <div class="col-sm-6">
                    <Input  
                        name={"Nama"}
                        placeholder={"Masukkan Nama.."}
                        id={"nama-konsumen"}
                        type={"text"}
                    />
                </div>
                <div class="col-sm-6">
                    <Input  
                        name={"Email"}
                        placeholder={"Masukkan Email.."}
                        id={"email-konsumen"}
                        type={"email"}
                    />
                </div>
                <div class="col-sm-6">
                    <Input  
                        name={"Password"}
                        placeholder={"Masukkan Password.."}
                        id={"password-konsumen"}
                        type={"text"}
                    />
                </div>
                <div class="col-sm-6">
                    <Input  
                        name={"No HP"}
                        placeholder={"Masukkan No HP..."}
                        id={"nohp-konsumen"}
                        type={"number"}
                    />
                </div>
                <div class="col-sm-6">
                    <InputDropdowns
                        name={"Jenis Kelamin"}
                        options={[
                            { name: "Laki - Laki", value: "lakilaki" },
                            { name: "Perempuan", value: "perempuan" }
                        ]}
                    />
                </div>
                <div class="col-sm-6">
                    <InputImages name={"Input Foto"} />
                </div>
            </div>
            <div class="d-flex justify-content-between mt-5">
                <a href="data-pengguna" class="btn btn-outline-danger">
                    Kembali
                </a>
                <button type="submit" class="btn btn-primary">
                    Simpan
                </button>
            </div>
        </form>
    </section>    
</MainTemplate>