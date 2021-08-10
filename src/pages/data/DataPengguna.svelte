<script>
    import CardDashboard from "../../components/dashboard/CardDashboard.svelte";
    import DashboardHeading from "../../components/dashboard/DashboardHeading.svelte";
    import MainTemplate from "../../templates/MainTemplate.svelte";
    import { Datatable, rows } from 'svelte-simple-datatables';
    import ButtonModal from "../../components/forms/ButtonModal.svelte";
    import Modal from "../../templates/Modal.svelte";
    import Input from "../../components/forms/Input.svelte";
    import InputDropdowns from "../../components/forms/InputDropdowns.svelte";
    import InputImages from "../../components/forms/InputImages.svelte";

    let dataUsers = [
        {
            id: "1",
            fotoUser: "https://dummyimage.com/100x100/4f4f4f/d1d1d1&text=Foto+User",
            nama: "John Doe",
            nomorHP: "081234567890",
            email: "johndoe@mail.com",
            jenisKelamin: "Laki - Laki"
        },
        {
            id: "2",
            fotoUser: "https://dummyimage.com/100x100/4f4f4f/d1d1d1&text=Foto+User",
            nama: "Jane Doe",
            nomorHP: "081234567890",
            email: "janedoe@mail.com",
            jenisKelamin: "Perempuan"
        }        
    ];
    const settings = {
        sortable: true,
        pagination: true,
        rowPerPage: 50,
        columnFilter: true,
    };
</script>

<style>
    td{
        text-align:center;padding:4px 0
    }
</style>

<MainTemplate>
    <DashboardHeading name={"Data Konsumen"} />
    <CardDashboard name={"Konsumen"} addUrl={"tambah-konsumen"}>
        <div class="card-body" style="height: 500px;">
            <Datatable settings={settings} data={dataUsers}>
                <thead>
                    <tr>
                        <th data-key="id">ID Konsumen</th>
                        <th data-key="fotoUser">Foto Konsumen</th>
                        <th data-key="nama">Nama</th>
                        <th data-key="nomorHP">Nomor HP</th>
                        <th data-key="email">Email</th>
                        <th data-key="jenisKelamin">Jenis Kelamin</th>
                        <th>Aksi</th>                        
                    </tr>
                </thead>
                <tbody>
                    {#each $rows as row }
                        <tr>
                            <td>{row.id}</td>
                            <td>
                                <img 
                                    src="{row.fotoUser}" 
                                    alt="{row.nama}"
                                    class="img-table"
                                    style="max-width: 90%;"
                                />
                            </td>
                            <td>
                                <a href="detail-pengguna">
                                    {row.nama}
                                </a>
                            </td>
                            <td>{row.nomorHP}</td>
                            <td>{row.email}</td>
                            <td>{row.jenisKelamin}</td>
                            <td class="d-flex justify-content-around">
                                <ButtonModal name={"Edit"} target={"edit-konsumen"} />
                                <a href="#" class="btn btn-outline-danger">
                                    Hapus
                                </a>
                            </td>
                        </tr>
                    {/each}                    
                </tbody>
            </Datatable>            
        </div>
    </CardDashboard>
</MainTemplate>
<Modal title={"Edit Konsumen"} idModal={"edit-konsumen"}>
    <div class="modal-body">
        <form>
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
                <button type="submit" class="btn btn-primary">
                    Simpan
                </button>
            </div>
        </form>
    </div>
</Modal>