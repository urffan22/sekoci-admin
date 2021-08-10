<script>
    export let name, addUrl = "";

    function downloadCSV(csv, filename) {
        var csvFile;
        var downloadLink;

        // CSV file
        csvFile = new Blob([csv], {type: "text/csv"});

        // Download link
        downloadLink = document.createElement("a");

        // File name
        downloadLink.download = filename;

        // Create a link to the file
        downloadLink.href = window.URL.createObjectURL(csvFile);

        // Hide download link
        downloadLink.style.display = "none";

        // Add the link to DOM
        document.body.appendChild(downloadLink);

        // Click download link
        downloadLink.click();
    }               

    function exportTableToCSV(filename) {
        var csv = [];
        var rows = document.querySelectorAll("table tr");
        
        for (var i = 0; i < rows.length; i++) {
            var row = [], cols = rows[i].querySelectorAll("td, th");
            
            for (var j = 0; j < cols.length; j++) 
                row.push(cols[j].innerText);
            
            csv.push(row.join(","));		
        }

        // Download CSV file
        downloadCSV(csv.join("\n"), filename);
    }

    function doHello() {
        alert("OK");
    }
</script>
<div class="card shadow mb-4">
    <div class="card-header py-3 d-flex justify-content-between align-items-center">
        <h6 class="m-0 font-weight-bold text-primary">Data {name}</h6>
        <div>
            {#if addUrl == ""}
            <span></span>
            {:else}
                <a href="{addUrl}" class="d-none d-sm-inline-block btn btn-sm btn-primary shadow-sm text-white">
                    <i class="fas fa-plus fa-sm text-white-50"></i>
                    <span>Tambah Data {name}</span>
                </a>
            {/if}
            <button class="btn btn-sm btn-outline-success" on:click={() => exportTableToCSV("table.csv")}>Export ke CSV</button>
        </div>
    </div>
    <slot></slot>
</div>