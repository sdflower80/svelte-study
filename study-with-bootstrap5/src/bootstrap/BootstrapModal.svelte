<script>
    import * as bootstrap from "bootstrap";

    document.addEventListener("DOMContentLoaded", function(){
        const btn = new bootstrap.Button(document.getElementById("sampleBtn"));
        btn.toggle();

    });

    function handleModal() {
        const myModal = new bootstrap.Modal(document.getElementById('exampleModal'), {})
        myModal.show();
    }
</script>

<main>
    <a href="#" id="sampleBtn" class="btn btn-primary active" role="button" data-bs-toggle="button" aria-pressed="false"
       onclick="console.log(111)">Active toggle link</a>


    <!-- Button trigger modal -->
    <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
        Launch demo modal
    </button>

    <button type="button" class="btn btn-primary" on:click={handleModal}>
        Launch demo modal2
    </button>

    <!-- Modal -->
    <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body">
                    ...
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                    <button type="button" class="btn btn-primary">Save changes</button>
                </div>
            </div>
        </div>
    </div>
</main>