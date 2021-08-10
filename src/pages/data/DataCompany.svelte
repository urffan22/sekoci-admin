<script>
import CardDashboard from "../../components/dashboard/CardDashboard.svelte";
import DashboardHeading from "../../components/dashboard/DashboardHeading.svelte";
import Input from "../../components/forms/Input.svelte";
import InputImages from "../../components/forms/InputImages.svelte";
import MainTemplate from "../../templates/MainTemplate.svelte";


</script>
<MainTemplate>
    <DashboardHeading name={"Data Company"} />
    <CardDashboard name={"Company"}>
        <section class="mb-4 px-4 py-2">
            <form class="">
                <div class="row">
                    <div class="col-sm-6">
                        <InputImages name={"Logo Company"} />
                    </div>
                    <div class="col-sm-6">
                        <Input 
                            name={"Nama Company"} 
                            id={"nama-company"}
                            type={"text"}
                            placeholder={"Masukkan Nama Company..."}
                        />
                    </div>
                    <div class="col-sm-6">
                        <Input 
                            name={"Email Company"} 
                            id={"email-company"}
                            type={"email"}
                            placeholder={"Masukkan Email Company..."}
                        />
                    </div>
                    <div class="col-sm-6">
                        <Input 
                            name={"Nomor Company"} 
                            id={"nomor-company"}
                            type={"number"}
                            placeholder={"Masukkan Nomor Company..."}
                        />
                    </div>
                    <div class="col-sm-6">
                        <Input 
                            name={"Alamat Companny"} 
                            id={"alamat-company"}
                            type={"text"}
                            placeholder={"Masukkan Alamat Companny..."}
                        />
                    </div>
                    <div class="col-sm-6">
                        <Input 
                            name={"Koordinat Company"} 
                            id={"koordinat-company"}
                            type={"text"}
                            placeholder={"Masukkan Koordinat Company..."}
                        />
                    </div>
                </div>
                <a href="#" class="btn btn-primary mt-4">
                    Simpan
                </a>
            </form>
        </section>
    </CardDashboard>
</MainTemplate>
