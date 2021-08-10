<script>
    import CardDashboard from "../../components/dashboard/CardDashboard.svelte";
    import DashboardHeading from "../../components/dashboard/DashboardHeading.svelte";
    import MainTemplate from "../../templates/MainTemplate.svelte";
    import { Datatable, rows } from 'svelte-simple-datatables';

    let dataAdmins = [
        {
            idAdmin: "1",
            nama: "Admin 1",
            email: "admin1@gmail.com"
        },
        {
            idAdmin: "2",
            nama: "Admin 2",
            email: "admin2@gmail.com"
        },
        {
            idAdmin: "3",
            nama: "Admin 3",
            email: "admin3@gmail.com"
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
    <DashboardHeading name={"Data Admin"} />
    <CardDashboard name={"Admin"} addUrl={"tambah-admin"} >
        <div style="height: 500px;" class="card-body">
            <Datatable data={dataAdmins} settings={settings}>
                <thead>
                    <th data-key="idAdmin">ID</th>
                    <th data-key="nama">Nama</th>
                    <th data-key="email">Email</th>                    
                </thead>
                <tbody>
                    {#each $rows as row}
                        <tr>
                            <td>{row.idAdmin}</td>
                            <td>{row.nama}</td>
                            <td>{row.email}</td>
                        </tr>
                    {/each}
                </tbody>
            </Datatable>
            <!-- <table id="dataAdmin" class="table table-striped table-bordered" style="width:100%">
                <thead>
                    <tr>
                        <th>ID Admin</th>
                        <th>Nama</th>
                        <th>Email</th>
                        <th>Aksi</th>
                    </tr>
                </thead>
                <tbody>
                    {#each dataAdmins as dataAdmin }
                    <tr>
                        <td>{dataAdmin.idAdmin}</td>
                        <td>{dataAdmin.nama}</td>
                        <td>{dataAdmin.email}</td>
                        <td class="d-flex justify-content-around">
                            <a href="#" class="btn btn-success">
                                Edit
                            </a>
                            <a href="#" class="btn btn-outline-danger">
                                Hapus
                            </a>
                        </td>
                    </tr>
                    {/each}                    
                </tbody>
            </table> -->
        </div>
    </CardDashboard>
</MainTemplate>