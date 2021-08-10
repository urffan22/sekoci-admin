<script>
    import CardDashboard from "../../components/dashboard/CardDashboard.svelte";
    import DashboardHeading from "../../components/dashboard/DashboardHeading.svelte";
    import MainTemplate from "../../templates/MainTemplate.svelte";
    import { Datatable, rows } from 'svelte-simple-datatables';
    import ButtonModal from "../../components/forms/ButtonModal.svelte";
    import Modal from "../../templates/Modal.svelte";
    import InputImages from "../../components/forms/InputImages.svelte";
    import Input from "../../components/forms/Input.svelte";
    let listSliders = [
        {
            id: "1",
            gambar: "https://dummyimage.com/400x200/8a8a8a/fff&text=Slider",
            nama: "Slider 1"
        },
        {
            id: "2",
            gambar: "https://dummyimage.com/400x200/8a8a8a/fff&text=Slider",
            nama: "Slider 2"
        },
        {
            id: "3",
            gambar: "https://dummyimage.com/400x200/8a8a8a/fff&text=Slider",
            nama: "Slider 3"
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
    <DashboardHeading name={"Data Slider"} />
    <CardDashboard name={"Slider"} addUrl={"tambah-slider"}>
    <div class="card-body" style="height: 500px;">
        <Datatable settings={settings} data={listSliders}>
            <thead>
                <tr>
                    <th data-key="id"  style="max-width: 20%;">ID Slider</th>
                    <th data-key="gambar">Gambar Slider</th>
                    <th data-key="nama">Nama Slider</th>
                    <th>Aksi</th>
                </tr>
            </thead>
            <tbody>
                {#each $rows as row }
                    <tr>
                        <td>{row.id}</td>
                        <td>
                            <img src="{row.gambar}" alt="gambar-slider" class="img-fluid" style="max-width: 200px;">
                        </td>
                        <td>{ row.nama }</td>           
                        <td class="d-flex justify-content-around">
                            <ButtonModal name={"Edit"} target={"edit-slider"} />
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

<Modal title={"Edit Slider"} idModal={"edit-slider"}>
    <div class="modal-body">
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
                <button type="submit" class="btn btn-primary">
                    Simpan
                </button>
            </div>
        </form>
    </div>
</Modal>