<script>
    import Card from '../components/dashboard/Card.svelte';    
    import DashboardHeading from '../components/dashboard/DashboardHeading.svelte';
    import Wrapper from '../components/slot/Wrapper.svelte';
    import MainTemplate from '../templates/MainTemplate.svelte';        

    let dataCards = [
        {
            color: "danger",
            name: "Total Menu",
            value: "100",
            icon: "utensils"
        },
        {
            color: "primary",
            name: "Total Pelanggan",
            value: "500",
            icon: "users"
        },
        {
            color: "warning",
            name: "Orderan Hari Ini",
            value: "200",
            icon: "truck"
        },
        {
            color: "success",
            name: "Omzet Bulan Ini",
            value: "1.000.000",
            icon: "money-bill"
        }
    ]
</script>

<MainTemplate>
    <!-- Main Content -->
    <Wrapper idName={"content"}>
        <!-- Begin Page Content -->
        <Wrapper className={"container-fluid"}>
            <DashboardHeading name={"Dashboard"} />
            <!-- Content Row -->
            <Wrapper className={"row"}>
                {#each dataCards as dataCard}
                    <Card {...dataCard} />
                {/each}                    
            </Wrapper>
        </Wrapper>
        <!-- /.container-fluid -->
    </Wrapper>
    <!-- End of Main Content -->
</MainTemplate>