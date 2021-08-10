<script>
    import Footer from "../components/footer/Footer.svelte";    
    import Header from "../components/header/Header.svelte";
    import Sidebar from "../components/sidebar/Sidebar.svelte";
    import Wrapper from "../components/slot/Wrapper.svelte";
    import Topbar from "../components/topbar/Topbar.svelte";
    import LogoutModal from "../components/utils/LogoutModal.svelte";
    import ScrollTopButton from "../components/utils/ScrollTopButton.svelte";
</script>

<!-- Page Wrapper -->
<Wrapper idName={"wrapper"}>
    <Header />    
    <!-- Sidebar -->
    <Sidebar />
    <!-- End of Sidebar -->
    <!-- Content Wrapper -->
    <Wrapper idName={"content-wrapper"} className={"d-flex flex-column"}>
        <!-- Main Content -->
        <Wrapper idName={"content"}>
            <Topbar />
            <!-- Begin Page Content -->
            <Wrapper className={"container-fluid"}>
                <slot>
                </slot>
            </Wrapper>
            <!-- /.container-fluid -->
        </Wrapper>
        <!-- End of Main Content -->
        <Footer name={"Neosantara"} year={"2021"} />
    </Wrapper>
    <!-- End of Content Wrapper -->
</Wrapper>
<!-- End of Page Wrapper -->

<ScrollTopButton />

<LogoutModal />