<script>
    let envProps = [
        {key: "a", value: "ttt"},
        {key: "b", value: "ttt"},
        {key: "c", value: "ttt"},
        {key: "d", value: "ttt"},
        {key: "e", value: "ttt"},
        {key: "f", value: "ttt"},
        {key: "g", value: "ttt"},
    ];

    function expandTextarea(event) {
        console.log("btn", event);

    }
</script>

<main>
    <h1>Setting UI</h1>
    <table class="table">
        <thead class="table-light">
        <tr>
            <th scope="col">#</th>
            <th scope="col">Key</th>
            <th scope="col">Value</th>
        </tr>
        </thead>
        <tbody>
        {#each envProps as p, i}
            <tr>
                <th scope="row">{i+1}</th>
                <td>{p.key}</td>
                <td>
                    <div class="container">
                        <div class="row justify-content-start">
                            <div class="col-6">
                                <textarea class="form-control" id="exampleFormControlTextarea1" rows="1">{p.value}</textarea>
                            </div>
                            <div class="col-3">
                                <button class="btn btn-primary btn-sm" type="button" on:click={expandTextarea}>확장</button>
                            </div>
                        </div>
                    </div>
                </td>
            </tr>
        {/each}
        </tbody>
    </table>
</main>

<style>

</style>