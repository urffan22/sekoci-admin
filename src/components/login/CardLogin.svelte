<script>
    import Wrapper from '../slot/Wrapper.svelte';
    import ButtonLogin from './utils/ButtonLogin.svelte';
    import CardTitle from './utils/CardTitle.svelte';
    import Checkbox from './utils/Checkbox.svelte';
    import Input from './utils/Input.svelte';
</script>

<style>
    .bg-login-image {
        background-image: url('https://images.unsplash.com/photo-1534080564583-6be75777b70a?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=750&q=80');
    }
    .card {
        margin-top: 15% !important;
    }
</style>

<section class="card o-hidden border-0 shadow-lg my-5">
    <Wrapper className="card-body p-0">
        <!-- Nested Row within Card Body -->
        <Wrapper className="row">
            <!-- Aside Image -->
            <div class="col-lg-6 d-none d-lg-block bg-login-image"></div>
            <!-- /Aside Image -->
            <Wrapper className="col-lg-6">
                <Wrapper className="p-5">
                    <!-- Content Form Login -->
                    <!-- Content Form Login -->
                    <!-- Content Form Login -->
                    <CardTitle name={"Sekoci Admin"} />
                    <form class="user">
                        <Input type={"email"} idName={"email"} placeholder={"Masukkan Email..."} />
                        <Input type={"password"} idName={"password"} placeholder={"Masukkan Password..."} />
                        <!-- <Checkbox idName={"rememberMe"} labelName={"Ingat Saya"} /> -->
                        <ButtonLogin href={"/"} name={"Login"} />
                    </form>
                    <!-- /Content Form Login -->
                    <!-- /Content Form Login -->
                    <!-- /Content Form Login -->
                </Wrapper>
            </Wrapper>
        </Wrapper>
    </Wrapper>
</section>