<script>
    export let color, icon, name, badgeCounter, notifications;
</script>

<!-- Nav Item - Alerts -->
<li class="nav-item dropdown no-arrow mx-1">
    <a class="nav-link dropdown-toggle" href="#" id="alertsDropdown" role="button"
        data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        <i class="fas fa-bell fa-fw"></i>
        <!-- Counter - Alerts -->
        <span class="badge badge-danger badge-counter">{badgeCounter}</span>
    </a>
    <!-- Dropdown - Alerts -->
    <div class="dropdown-list dropdown-menu dropdown-menu-right shadow animated--grow-in"
        aria-labelledby="alertsDropdown">
        <h6 class="dropdown-header">
            {name}
        </h6>
        {#each notifications as notification }
            <a class="dropdown-item d-flex align-items-center" href="#">
                <div class="mr-3">
                    <div class="icon-circle bg-{color}">
                        <i class="fas fa-{icon} text-white"></i>
                    </div>
                </div>
                <div>
                    <div class="small text-gray-500">{notification.tanggal}</div>
                    <span class="font-weight-bold">{notification.content}</span>
                </div>
            </a>
        {/each}        
    </div>
</li>