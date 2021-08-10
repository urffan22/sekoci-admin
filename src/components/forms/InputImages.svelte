<script>
    export let name;
	let avatar, fileinput, id;
	
	const onFileSelected =(e)=>{
        let image = e.target.files[0];
        let reader = new FileReader();
        reader.readAsDataURL(image);
        reader.onload = e => {
            avatar = e.target.result;
        };
    }
	
</script>

<style>
    img {
        width: 200px;
    }
</style>

<div>
	<div class="d-flex flex-column">
        <span>
            {name}
        </span> 
        {#if avatar}
            <img class="avatar" src="{avatar}" alt="d" />
        {:else}
        <img 
            class="avatar" 
            src="https://dummyimage.com/600x400/d4d4d4/858585&text=Upload+{name}" alt=""
            on:click={()=>{fileinput.click();}}
        /> 
        {/if}
    </div>
    <div class="btn btn-outline-success mt-2" on:click={()=>{fileinput.click();}}>
        Upload Gambar
    </div>
    <input 
        style="display:none"
        type="file"
        accept=".jpg, .jpeg, .png"
        id="{id}"
        on:change={(e)=>onFileSelected(e)} bind:this={fileinput} 
    />
</div>