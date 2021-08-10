<script>
    import CardDashboard from "../../components/dashboard/CardDashboard.svelte";
    import DashboardHeading from "../../components/dashboard/DashboardHeading.svelte";
    import ButtonModal from "../../components/forms/ButtonModal.svelte";
    import MainTemplate from "../../templates/MainTemplate.svelte";
    import Modal from "../../templates/Modal.svelte";
    import { Datatable, rows } from 'svelte-simple-datatables';

    let listOrders = [
        {
            id: 1,
            username: "John Doe",
            data_order_time: "11:02/27-07-2021",
            alamat: "Jalan Moch Hatta Nomor.10",
            order_status: "Proses",
            payment_status: "Belum Bayar"
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
    <DashboardHeading name={"Data Transaksi"} />
    <CardDashboard name={"Transaksi"}>
        <div class="card-body" style="height: 500px;">
            <Datatable settings={settings} data={listOrders} >
                <thead>
                    <tr>
                        <th data-key="id" style="width: 10%;">ID Order</th>
                        <th data-key="username">Username</th>
                        <th data-key="data_order_time" style="width: 10%;">Waktu</th>
                        <th data-key="alamat">Alamat</th>                        
                        <th data-key="order_status">Order Status</th>
                        <th data-key="payment_status">Payment Status</th>
                        <th>Aksi</th>
                    </tr>
                </thead>
                <tbody>
                    {#each $rows as row }
                        <tr>
                            <td>{row.id}</td>
                            <td>{row.username}</td>
                            <td>{row.data_order_time}</td>
                            <td>{row.alamat}</td>
                            <td>{row.order_status}</td>
                            <td>{row.payment_status}</td>
                            <td>
                                <ButtonModal target={"detail-order"} name={"Detail Pesanan"} />
                            </td>
                        </tr>
                    {/each}
                </tbody>
            </Datatable>
        </div>        
    </CardDashboard>
</MainTemplate>

<!-- Modal -->
<Modal idModal={"detail-order"} title={"ID Order: 1"}>
    <div class="modal-body">
        <h4>Data Pemesan</h4>
        <table class="table table-striped table-bordered">
            <thead>
                <tr>
                    <th>Username</th>
                    <th>Waktu Tanggal Pesanan</th>
                    <th>Metode Pembayaran</th>
                    <th>Alamat</th>
                    <th>Jarak Pesanan</th>
                    <th>Catatan</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>John Doe</td>
                    <td>11:02/27-07-2021</td>
                    <td>Cash On Delivery</td>
                    <td>Jalan Moch Hatta Nomor.10</td>
                    <td>1.5 KM</td>
                    <td>Tolong simpan di depan pagar</td>                    
                </tr>
            </tbody>
        </table>
        <h4 class="mt-5">Data Pesanan</h4>
        <table class="table table-striped table-bordered">
            <thead>
                <tr>
                    <th>ID Produk</th>
                    <th>Nama Produk</th>
                    <th>Jumlah Produk</th>
                    <th>Total Harga</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>1</td>
                    <td>Lobster Goreng</td>
                    <td>2</td>
                    <td>200000</td>
                </tr>
                <tr>
                    <td>2</td>
                    <td>Jus Jeruk</td>
                    <td>1</td>
                    <td>10000</td>
                </tr>
                <tr>
                    <th>Total Harga Pesanan</th>
                    <td>210000</td>
                    <th>Ongkir</th>
                    <td>10000</td>
                </tr>             
            </tbody>
        </table>
        <h4 class="mt-5">Data Harga</h4>
        <table class="table table-striped table-bordered">
            <thead>
                <tr>
                    <th>Potongan Harga</th>
                    <th>Total Harga</th>
                    <th>Status Pengantaran</th>
                    <th>Status Pembayaran</th>                        
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>10%</td>
                    <td>190000</td>
                    <td>
                        <div class="form-group">
                            <label for="status-pengantaran">Pilih Status Pengantaran</label>
                            <select class="form-control" id="status-pengantaran">
                                <option>Proses</option>
                                <option>Dalam Perjalanan</option>
                                <option>Selesai</option>
                            </select>
                        </div>
                    </td>
                    <td>
                        <div class="form-group">
                            <label for="status-pembayaran">Pilih Status Pembayaran</label>
                            <select class="form-control" id="status-pembayaran">
                                <option>Sudah</option>
                                <option>Belum</option>
                                <option>Selesai</option>
                            </select>
                        </div>
                    </td>                
                </tr>
            </tbody>
        </table>
    </div>
    <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">
            Close
        </button>
        <button type="button" class="btn btn-primary">
            Simpan
        </button>
    </div>
</Modal>