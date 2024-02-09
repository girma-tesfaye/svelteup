<script>
    export let showModal = false;
    export let message = "This is default"
</script>

{#if showModal}
   <div class="backdrop">
        <div class="modal">
            <p>{message}</p>
        </div>
    </div> 
{/if}


<style>
    .backdrop{
        width: 100%;
        position: absolute;
        background: rgba(0, 0, 0, 0.8);
        margin: 0;
        padding: 0;
        height: 100%;
    }
    .modal {
        width: 400px;
        background: white;
        text-align: center;
        margin: 10% auto;
        padding: 10px;
        border: none;
        border-radius: 5px;
    }
</style>