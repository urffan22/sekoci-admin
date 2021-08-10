<script>
    import Header from '../components/header/Header.svelte';
    import CardLogin from '../components/login/CardLogin.svelte';
    import Wrapper from '../components/slot/Wrapper.svelte';    
</script>

<style>
    .bgLogin {
        height: 100vh;
        background-image: linear-gradient(#F15656, #992020d0);
    }
</style>
<section class="bgLogin">
    <Header/>    
    <Wrapper className="container">
        <Wrapper className="row justify-content-center">
            <Wrapper className="col-xl-10 col-lg-12 col-md-9">
                <!-- Bagian Card Login -->
                <!-- Bagian Card Login -->
                <!-- Bagian Card Login -->
                <CardLogin />
                <!-- /Bagian Card Login -->
                <!-- /Bagian Card Login -->
                <!-- /Bagian Card Login -->
            </Wrapper>
        </Wrapper>
    </Wrapper>
</section>

