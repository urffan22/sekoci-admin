<script>
	// imports Routing
	import { Router, Route } from 'svelte-routing';
	import { links } from "svelte-routing";
	// Import Login & Home
	import Login from './pages/Login.svelte';
	import Home from './pages/Home.svelte';	
	// imports Data
	import DataPengguna from './pages/data/DataPengguna.svelte';
	import DataMenu from './pages/data/DataMenu.svelte';
	import TambahMenu from './pages/tambah/TambahMenu.svelte';
	// imports Tambah Data
	import Entarance from './pages/tambah/TambahEntrance.svelte';
	import Onboarding from './pages/tambah/TambahOnboarding.svelte';
	import DataMenuKategori from './pages/data/DataMenuKategori.svelte';
	import TambahMenuCategory from './pages/tambah/TambahMenuCategory.svelte';
	import TambahKonsumen from './pages/tambah/TambahKonsumen.svelte';
	import DataTransaksi from './pages/data/DataTransaksi.svelte';
	import DataAdmin from './pages/data/DataAdmin.svelte';
	import TambahAdmin from './pages/tambah/TambahAdmin.svelte';
	import DataSlider from './pages/data/DataSlider.svelte';
	import TambahSlider from './pages/tambah/TambahSlider.svelte';	
	import DataCompany from './pages/data/DataCompany.svelte';
	import DataEntrance from './pages/data/DataEntrance.svelte';
	import DataOnboarding from './pages/data/DataOnboarding.svelte';
	
	// exports
	export let url = '';	
</script>

<div use:links>
	<Router url="{url}">	
		<!-- Login -->
		<Route path="login" component="{Login}" />	
		<!-- Dashboard -->
		<Route path="/" component="{Home}" />
		<!-- Splashscreen -->
		<Route path="entrance" component="{DataEntrance}" />
		<Route path="tambah-entrance" component="{Entarance}" />
		<Route path="onboarding" component="{DataOnboarding}" />
		<Route path="tambah-onboarding" component="{Onboarding}" />
		<!-- Menu -->
		<Route path="menu" component="{DataMenu}" />
		<Route path="tambah-menu" component="{TambahMenu}" />
		<!-- Menu Kategori -->
		<Route path="menu-kategori" component="{DataMenuKategori}" />
		<Route path="tambah-menu-kategori" component="{TambahMenuCategory}" />
		<!-- Data Pengguna -->
		<Route path="data-pengguna" component="{DataPengguna}" />
		<Route path="tambah-konsumen" component="{TambahKonsumen}" />
		<!-- Data transaksi -->
		<Route path="data-transaksi" component="{DataTransaksi}" />
		<!-- Data Company -->
		<Route path="company" component="{DataCompany}" />
		<!-- Data Admin -->
		<Route path="admin" component="{DataAdmin}" />
		<Route path="tambah-admin" component="{TambahAdmin}" />
		<!-- Data Slider -->
		<Route path="slider" component="{DataSlider}" />
		<Route path="tambah-slider" component="{TambahSlider}" />
		
	</Router>
</div>