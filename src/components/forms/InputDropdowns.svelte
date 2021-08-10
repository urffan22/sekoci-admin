<script>
    export let name, category_id, options;
</script>
<div class="form-group">
    <label for="{category_id}">{name}</label>
    <select class="form-control" id="{category_id}">
        {#each options as option }
            <option value="val-{option.value}">{option.name}</option>
        {/each}                  
    </select>
</div>