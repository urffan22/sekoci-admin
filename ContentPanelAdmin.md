Dashboard
[Data Master]
Menu Kategori
Menu
Konsumen

[Data Order]
Transaksi

Pengaturan
	Company
	Admin
	SplashScreen
	Slider
	
	

**** MENU ****
Dashboard
	Total Menu, Total Pelanggan, Order Hari ini, Omzet Bulan Ini
	[*] Statistik [Per bulan: selected bulan ini, tapi bisa pilih bulan yang lain]
		:[dalam statistik data pertanggal]

Menu Kategori
	List Kategori
		Id, Title, Img, Total Item
	Add Kategori
		Title, Img
	Edit Kategori
		Title, Img

Menu
	List Menu
		id, cateogory, title, image, price, aksi (edit, delete, unpublish/publish)
	Add Menu
		id_category, title, subtitle, description, price, discount, published
	Edit Menu
		id_category, title, subtitle, description, price, discount, published

Konsumen
	List Konsumen
		id_user, name, email, phone, gender, foto
	Add Konsumen
		name, email, password, phone, gender, foto
	Edit Konsumen
		name, email, password, phone, gender, foto

Transaksi
	List Transaksi
		Id Order, User-name, date-order time, address, total_price, order-status, payment-status
			[
				id_order, date_order, time_order, id_voucher, discount_price, total_price, payment_method, payment_status, note
				id_user, -> nama user dll nya muncul
				id_address, -> rincian alamat muncul
			]
			
		id_order, id_user, date_order, time_order, id_address, id_voucher, discount_price, total_price, payment_method, payment_status, note