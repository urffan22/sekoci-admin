<script>
    export let type, idName, placeholder;
</script>

<style>
    .form-group input {
        border-radius: 6px !important;
    }
</style>

<div class="form-group">
    <input 
    type="{type}"
    class="form-control form-control-user"
    id="{idName}"
    placeholder="{placeholder}" />
</div>