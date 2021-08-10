<script>
    export let name, href = "", icon;
</script>

<li class="nav-item">
    <a class="nav-link" href="{href}">
        <i class="fas fa-fw fa-{icon}"></i>
        <span>{name}</span>
    </a>
</li>