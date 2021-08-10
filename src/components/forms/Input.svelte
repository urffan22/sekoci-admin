<script>
    export let name, placeholder, id, type, value="";
</script>
<div class="form-group">
    <label for="input-{id}">{name}</label>
    <input 
        placeholder="{placeholder}" 
        type="{type}" 
        min="0" 
        class="form-control" 
        id="input-{id}"
        value="{value}"
    />
</div>