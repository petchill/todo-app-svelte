<script lang="ts">
  // TODO: add variable isShow
</script>

<!-- TODO: add if show -->
<!-- TODO: add onclick|self -->
<div class="backdrop">
  <div class="modal">
    <slot name="title" />
    <slot name="subtitle" />
    <slot />
  </div>
</div>

<style>
  .backdrop {
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.8);
    position: fixed;
  }

  .modal {
    padding: 10px;
    border-radius: 10px;
    max-width: 400px;
    margin: 10% auto;
    background: white;
    text-align: center;
  }
</style>
