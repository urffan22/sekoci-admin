<script>
    import { Datatable, rows } from 'svelte-simple-datatables';
    import CardDashboard from '../../components/dashboard/CardDashboard.svelte';
    import DashboardHeading from '../../components/dashboard/DashboardHeading.svelte';
import ButtonModal from '../../components/forms/ButtonModal.svelte';
import Input from '../../components/forms/Input.svelte';
import InputImages from '../../components/forms/InputImages.svelte';
    import MainTemplate from '../../templates/MainTemplate.svelte';
import Modal from '../../templates/Modal.svelte';
    let dataOnboardings = [
        {
            gambar: "https://dummyimage.com/600x800/000/e0e0e0&text=Foto+Onboarding",
            urutan: "1",
            judul: "Onboarding - 1",
            deskripsi: "Onboarding yang ke-1"
        },
        {
            gambar: "https://dummyimage.com/600x800/000/e0e0e0&text=Foto+Onboarding",
            urutan: "2",
            judul: "Onboarding - 2",
            deskripsi: "Onboarding yang ke-2"
        },
        {
            gambar: "https://dummyimage.com/600x800/000/e0e0e0&text=Foto+Onboarding",
            urutan: "3",
            judul: "Onboarding - 3",
            deskripsi: "Onboarding yang ke-3"
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
    <DashboardHeading name={"Onboarding"} />
    <!-- card Entrance -->
    <CardDashboard name={"Entrance"} addUrl={"tambah-onboarding"}>
        <div class="card-body" style="height: 800px;">
            <Datatable settings={settings} data={dataOnboardings}>
                <thead>
                    <tr>
                        <th data-key="gambar">Gambar</th>
                        <th data-key="urutan">Urutan</th>
                        <th data-key="judul">Judul</th>
                        <th data-key="deskripsi">Deskripsi</th>
                        <th class="text-center">Aksi</th>
                    </tr>                    
                </thead>
                <tbody>
                    {#each $rows as row }
                        <tr>
                            <td>
                                <img src="{row.gambar}" alt="on-boarding" style="max-width: 200px;">
                            </td>
                            <td>{row.urutan}</td>
                            <td>{row.judul}</td>
                            <td>{row.deskripsi}</td>
                            <td class="d-flex justify-content-around">
                                <ButtonModal name={"Edit"} target={"edit-onboarding"} />
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
    <!-- /card Entrance -->        
</MainTemplate>
<Modal title={"Edit Onboarding"} idModal={"edit-onboarding"} >
    <div class="modal-body">
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
                <button type="submit" class="btn btn-primary">
                    Simpan
                </button>
            </div>
        </form>
    </div>
</Modal>