<script>
    import CardDashboard from "../../components/dashboard/CardDashboard.svelte";
    import DashboardHeading from "../../components/dashboard/DashboardHeading.svelte";
    import MainTemplate from "../../templates/MainTemplate.svelte";
    import { Datatable, rows } from 'svelte-simple-datatables';
    import ButtonModal from "../../components/forms/ButtonModal.svelte";
    import Modal from "../../templates/Modal.svelte";
    import Input from "../../components/forms/Input.svelte";
    import InputImages from "../../components/forms/InputImages.svelte";

    let listCategories = [
        {
            id: "1",
            title: "Makanan Seafood",
            image: "https://dummyimage.com/600x400/999999/7a7a7a&text=Foto+Kategori",
            totalItem: "1"
        },
        {
            id: "2",
            title: "Minuman Seafood",
            image: "https://dummyimage.com/600x400/999999/7a7a7a&text=Foto+Kategori",
            totalItem: "1"
        }
    ];
    const settings = {
        sortable: true,
        pagination: true,
        rowPerPage: 50,
        columnFilter: false,
    };
</script>

<style>
    td{
        text-align:center;padding:4px 0
    }
</style>

<MainTemplate>
    <DashboardHeading name={"Data Menu Kategori"} />
    <CardDashboard name={"Menu Kategori"} addUrl={"tambah-menu-kategori"}>
        <div class="card-body" style="height: 500px;">
            <Datatable settings={settings} data={listCategories}>
                <thead>
                    <tr>
                        <th data-key="id" style="max-width: 10%;">Id</th>
                        <th data-key="title">Title</th>
                        <th data-key="image">Image</th>
                        <th data-key="totalItem">Total Item</th>
                        <th>Aksi</th>
                    </tr>
                </thead>
                <tbody>
                    {#each $rows as row }
                        <tr>
                            <td>{row.id}</td>
                            <td>{row.title}</td>
                            <td>
                                <img src="{row.image}" alt="foto-menu" class="img-fluid" style="max-width: 200px;">
                            </td>
                            <td>{row.totalItem}</td>
                            <td class="d-flex justify-content-around">
                                <ButtonModal target={"edit-menu-category"} name={"Edit"} />
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
<Modal idModal={"edit-menu-category"} title={"Edit Menu Kategori"} >
    <div class="modal-body">
        <section class="px-4 py-2">
            <form class="">
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
                    <button type="submit" class="btn btn-primary">
                        Simpan
                    </button>
                </div>
            </form>
        </section>
    </div>
</Modal>