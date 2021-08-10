<script>    
    import CardDashboard from '../../components/dashboard/CardDashboard.svelte';
    import DashboardHeading from '../../components/dashboard/DashboardHeading.svelte';
    import MainTemplate from '../../templates/MainTemplate.svelte';
    import { Datatable, rows } from 'svelte-simple-datatables';
    import ButtonModal from '../../components/forms/ButtonModal.svelte';
    import Modal from '../../templates/Modal.svelte';
    import Input from '../../components/forms/Input.svelte';
    import InputImages from '../../components/forms/InputImages.svelte';
    let dataEntrances = [
        {
            gambar: "https://dummyimage.com/100x100/4f4f4f/d1d1d1&text=Logo+Sekoci+Seafood",
            nama: "Logo",
            keterangan: "Logo Sekoci Seafood"
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
    .img-table {
        max-width: 90%;
    }
    td{
        text-align:center;padding:4px 0
    }
</style>

<MainTemplate>
    <DashboardHeading name={"Entrance"} />
    <!-- card Entrance -->
    <CardDashboard name={"Entrance"} addUrl={"tambah-entrance"}>
        <div class="card-body" style="height: 350px;">
            <Datatable settings={settings} data={dataEntrances}>
                <thead>
                    <tr>
                        <th data-key="gambar">Gambar</th>
                        <th data-key="nama">Nama</th>
                        <th data-key="keterangan">Keterangan</th>
                        <th class="text-center">Aksi</th>
                    </tr>
                </thead>
                <tbody>                    
                    {#each $rows as row }
                    <tr>
                        <td>
                            <img src="{row.gambar}" alt="" class="img-table">
                        </td>
                        <td>
                            { row.nama}
                        </td>
                        <td>
                            { row.keterangan }
                        </td>
                        <td class="d-flex justify-content-around">
                            <ButtonModal name={"Edit"} target={"edit-entrance"} />
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

<Modal title={"Edit Entrance"} idModal={"edit-entrance"} >
    <div class="modal-body">
        <form class="card-body">
            <div class="row">
                <div class="col-sm-6">
                    <Input 
                        name={"Nama Entrance"} 
                        placeholder={"Masukkan Nama Entrance..."} 
                        id={"entrance"}
                        type={"text"} 
                    />
                </div>
                <div class="col-sm-6">
                    <Input 
                        name={"Keterangan"} 
                        placeholder={"Masukkan Keterangan..."} 
                        id={"keterangan"}
                        type={"text"} 
                    />
                </div>
            </div>
            <div class="row">
                <div class="col-sm-6">                    
                    <InputImages name={"Upload Gambar Logo Sekoci"} />                      
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

