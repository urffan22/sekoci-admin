<script>
    // import from utils
    import Brand from './utils/Brand.svelte';
    import Heading from './utils/Heading.svelte';
    import Divider from './utils/Divider.svelte';
    import NavLink from './utils/NavLink.svelte';
    import DropdownNavLink from './utils/DropdownNavLink.svelte';
    
    /*
        Jika mau pakai komponen Dropdown dengan Link
        maka untuk childlinknya gunakan contoh sintaks ini:
        childLinks = {[
            {
                name: "nama childLink",
                href: "link-child-link"
            }
        ]}
    */
    
</script>

<style>
    aside {
        /* background-color: #F15656; */
        background-image: linear-gradient(#F15656, #992020d0);
    }
</style>

<aside class="navbar-nav sidebar sidebar-dark accordion" id="accordionSidebar">
    <!-- Brand -->
    <Brand name={"Sekoci Admin"} />
    <!-- /Brand -->
    <Divider />
    <!-- Heading Menu Dashboard -->
    <NavLink name={"Dashboard"} icon={"tachometer-alt"} href={"/"} />
    <Divider />    
    <!-- Judul Heading Umum -->
    <Heading name={"Data Master"} />
    <NavLink name={"Menu"} icon={"utensils"} href={"menu"} />
    <NavLink name={"Menu Kategori"} icon={"filter"} href={"menu-kategori"} />
    <NavLink name={"Konsumen"} icon={"users"} href={"data-pengguna"} />
    <!-- Judul Heading Umum -->
    <!-- Transaksi -->
    <Divider />
    <Heading name={"Transaksi"} />
    <NavLink name={"List Transaksi"} icon={"money-bill-wave"} href={"data-transaksi"} />
    <!-- /Transaksi -->
    <!-- /Heading Menu Umum -->
    <Divider />
    <Heading name={"Pengaturan"} />
    <DropdownNavLink name={"Pengaturan"} icon={"cog"}
        childLinks = {[
            {
                name: "Company",
                href: "company"
            },
            {
                name: "Admin",
                href: "admin"
            },
            {
                name: "Entrance",
                href: "entrance"
            },
            // {
            //     name: "On Boarding",
            //     href: "onboarding"
            // },
            // {
            //     name: "Slider",
            //     href: "slider"
            // }            
        ]}
    />
    <!-- Sidebar Toggler (Sidebar) -->
    <!-- <div class="text-center d-none d-md-inline">
        <button class="rounded-circle border-0" id="sidebarToggle"></button>
    </div> -->
</aside>