<script>
    export let showModal = false;
    export let message = "This is default";
    export let isPromo = false;
</script>

{#if showModal}
   <!-- svelte-ignore a11y-click-events-have-key-events -->
   <div class="backdrop" class:promo={isPromo} on:click|self>
        <div class="modal" >
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
    .promo {
        background: crimson;
    }
</style>