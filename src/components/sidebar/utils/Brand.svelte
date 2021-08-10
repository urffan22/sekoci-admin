<script>
    export let href, name;
</script>

<style>
    .sidebar-brand-text {
        font-size: 0.8em;
    }
</style>


<a class="sidebar-brand d-flex align-items-center justify-content-center" href="{href}">
    <div class="sidebar-brand-icon">
        <img src="./images/logo.png" alt="" style="width: 40px;">
    </div>
    <div class="sidebar-brand-text mx-3">
        {name}
    </div>
</a>