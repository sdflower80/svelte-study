<script>
    import * as bootstrap from "bootstrap";

    export let configureList;

    let collapseBsMap = {};

    const bindCollapse = (node) => {
        collapseBsMap[node.id] = new bootstrap.Collapse(node, {toggle: false});
    };

    const toggleCollapse = (id) => {
        collapseBsMap[id].toggle();
    };

    const openNewConfigureModal = () => {
        let m = new bootstrap.Modal(document.getElementById("newConfigureModal"));
        m.show();
    };

    let inputKey;
    let inputDesc;
    let inputValue;
    const saveConfigure = () => {
        let configure = {
            key: inputKey,
            desc: inputDesc,
            value: inputValue
        }

        configureList = [...configureList, configure];

        let m = bootstrap.Modal.getInstance(document.getElementById("newConfigureModal"))
        m.hide();
    };
</script>

<main>
    <div class="container-lg">
        <div class="row">
            <div class="col text-end py-1">
                <button class="btn btn-primary" type="button" on:click={() => {openNewConfigureModal();}}>New</button>
            </div>
        </div>
        <div class="row border-top border-bottom py-2">
            <div class="col-1">#</div>
            <div class="col-3">Key</div>
            <div class="col-5">Desc</div>
            <div class="col-3">Function</div>
        </div>
        {#each configureList as p, i}
            <div class="row border-bottom py-2">
                <div class="col-1 text-start pt-2">{i+1}</div>
                <div class="col-3 text-start pt-2">{p.key}</div>
                <div class="col-5 text-start pt-2">{p.desc}</div>
                <div class="col-3 text-end">
                    <button class="btn btn-primary" type="button" on:click={() => {toggleCollapse(p.key + "_edit")}}>Edit</button>
                    <button class="btn btn-primary" type="button">Delete</button>
                </div>
            </div>
            <div class="row">
                <div class="py-3 collapse" id="{p.key}_edit" use:bindCollapse>
                    <div class="card">
                        <div class="card-body">
                            <textarea class="form-control" id="{p.key}" rows="10">{p.value}</textarea>
                        </div>
                        <div class="card-footer text-end">
                            <button class="btn btn-primary" type="button">Save</button>
                        </div>
                    </div>
                </div>
            </div>
        {/each}
    </div>

    <div id="newConfigureModal" class="modal" tabindex="-1">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title">New Configure</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body">
                    <div class="input-group mb-3">
                        <span class="input-group-text">Key</span>
                        <input type="text" class="form-control" aria-label="input" bind:value={inputKey}>
                    </div>
                    <div class="input-group mb-3">
                        <span class="input-group-text">Desc</span>
                        <input type="text" class="form-control" aria-label="input" bind:value={inputDesc}>
                    </div>
                    <div class="input-group">
                        <span class="input-group-text">Value</span>
                        <textarea class="form-control" aria-label="textarea" rows="5" bind:value={inputValue}></textarea>
                    </div>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                    <button type="button" class="btn btn-primary" on:click={() => {saveConfigure();}}>Save</button>
                </div>
            </div>
        </div>
    </div>
</main>

<style>

</style>