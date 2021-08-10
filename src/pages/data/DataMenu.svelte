<script>
    import CardDashboard from "../../components/dashboard/CardDashboard.svelte";
    import DashboardHeading from "../../components/dashboard/DashboardHeading.svelte";
    import MainTemplate from "../../templates/MainTemplate.svelte";    
    import { Datatable, rows } from 'svelte-simple-datatables';
    import ButtonModal from "../../components/forms/ButtonModal.svelte";
    import Modal from "../../templates/Modal.svelte";    
    import InputDropdowns from "../../components/forms/InputDropdowns.svelte";
    import Input from "../../components/forms/Input.svelte";
    import RichText from "../../components/forms/RichText.svelte";
    import InputImages from "../../components/forms/InputImages.svelte";

    let dataMenus = [
        {
            id: 1,
            category: "Seafood",
            title: "Lobster Rebus",
            images: "https://dummyimage.com/600x400/999999/7a7a7a&text=Foto+Menu",
            price: "100000",
            rating: "5"            
        },
        {
            id: 2,
            category: "Minuman",
            title: "Jus Jeruk",
            images: "https://dummyimage.com/600x400/999999/7a7a7a&text=Foto+Menu",
            price: "10000",
            rating: "4.5"
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
    <DashboardHeading name={"Data Menu"} />
    <CardDashboard name={"Menu"} addUrl={"tambah-menu"}>
        <div class="card-body" style="height: 500px;">
            <Datatable data={dataMenus} settings={settings} >
                <thead>
                    <tr>
                        <th data-key="id">Id</th>
                        <th data-key="category">Category</th>
                        <th data-key="title">Title</th>
                        <th data-key="images">Images</th>
                        <th data-key="price">Price</th>
                        <th data-key="rating">Rating</th>
                        <th>Aksi</th>
                    </tr>
                </thead>
                <tbody>
                    {#each $rows as row }
                        <tr>
                            <td>{row.id}</td>
                            <td>{row.category}</td>
                            <td>{row.title}</td>
                            <td>
                                <img src="{row.images}" alt="foto-menu" class="img-fluid" style="max-width: 200px;">
                            </td>
                            <td>{row.price}</td>
                            <td>{row.rating}</td>
                            <td class="d-flex justify-content-around">
                                <ButtonModal name={"edit"} target={"edit-menu"} />
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
<Modal title={"Edit Menu"} idModal={"edit-menu"} >
    <div class="modal-body">
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
    </div>
</Modal>