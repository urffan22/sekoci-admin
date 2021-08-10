<script>
    // export let userName, imageUrl;    
    let getDataUser = {
        userName: "Sandra",
        imageUrl: "https://image.freepik.com/free-vector/businessman-character-avatar-isolated_24877-60111.jpg"
    }
</script>

<!-- Nav Item - User Information -->
<li class="nav-item dropdown no-arrow">
    <a class="nav-link dropdown-toggle" href="#" id="userDropdown" role="button"
        data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        <span class="mr-2 d-none d-lg-inline text-gray-600 small">
            {getDataUser.userName}
        </span>
        <img class="img-profile rounded-circle" src="{getDataUser.imageUrl}" alt="">
    </a>
    <!-- Dropdown - User Information -->
    <div class="dropdown-menu dropdown-menu-right shadow animated--grow-in"
        aria-labelledby="userDropdown">
        <a class="dropdown-item" href="login" data-toggle="modal" data-target="#logoutModal">
            <i class="fas fa-sign-out-alt fa-sm fa-fw mr-2 text-gray-400"></i>
            Logout
        </a>
    </div>
</li>