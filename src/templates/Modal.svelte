<script>
    import ModalHeader from "./utils/ModalHeader.svelte";
    export let idModal, title;
</script>

<div class="modal fade" id="{idModal}" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog modal-xl">
      <div class="modal-content">
        <ModalHeader modalTitle={title} />
        <slot></slot>
      </div>
    </div>
</div>