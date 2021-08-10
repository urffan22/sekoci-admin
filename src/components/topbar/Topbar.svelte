<script>
    import Divider from "./utils/micro/Divider.svelte";
    import Notification from "./utils/Notification.svelte";
    import SearchInput from "./utils/SearchInput.svelte";
    import SearchInputXs from "./utils/SearchInputXS.svelte";
    import UserInformation from "./utils/UserInformation.svelte";

    // bikin notifications
    let notifications = [
        {
            icon: "envelope",
            color: "primary",
            tanggal: "16-07-2021",
            content: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Incidunt, deleniti."
        },
        {
            icon: "envelope",
            color: "success",
            tanggal: "12-07-2021",
            content: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Incidunt, deleniti."
        }
    ]
</script>

<!-- Topbar -->
<nav class="navbar navbar-expand navbar-light bg-white topbar mb-4 static-top shadow">
    <!-- Sidebar Toggle (Topbar) -->
    <!-- <button id="sidebarToggleTop" class="btn btn-link d-md-none rounded-circle mr-3">
        <i class="fa fa-bars"></i>
    </button> -->
    <SearchInput />
    <!-- Topbar Navbar -->
    <ul class="navbar-nav ml-auto">
        <SearchInputXs />
        <Notification name={"Pemberitahuan"} badgeCounter={"3+"} notifications={notifications} />

        <Divider />

        <UserInformation />
    </ul>
</nav>
<!-- End of Topbar -->