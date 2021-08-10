<script>
    export let name, icon;
    export let childLinks;
</script>

<li class="nav-item">
    <a class="nav-link collapsed" href="#" data-toggle="collapse" data-target="#collapseTwo"
        aria-expanded="true" aria-controls="collapseTwo">
        <i class="fas fa-fw fa-{icon}"></i>
        <span>{name}</span>
    </a>
    <div id="collapseTwo" class="collapse" aria-labelledby="headingTwo" data-parent="#accordionSidebar">
        <div class="bg-white py-2 collapse-inner rounded">
            <h6 class="collapse-header">{name}:</h6>
            {#each childLinks as childLink}
                <a class="collapse-item" href="{childLink.href}">{childLink.name}</a>
            {/each}
        </div>
    </div>
</li>