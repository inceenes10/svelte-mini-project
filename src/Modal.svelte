<script>
    export let showModal = true;
    export let isPromo = false;
</script>

{#if showModal}
<div class="backdrop" class:promo={isPromo} on:click|self>
    <div class="modal">
        <slot></slot>
    </div>
</div>
{/if}

<style>
    .backdrop {
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0, 0, 0, 0.7);
        display: grid;
        place-content: center;
        cursor: pointer;
    }

    .modal {
        cursor: initial;
        width: 400px;
        padding: 10px;
        border-radius: 10px;
        text-align: center;
        background: white;
    }
    .promo .modal {
        background: crimson;
        color: white;
    }
</style>
