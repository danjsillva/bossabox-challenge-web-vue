<script>
export default {
  props: ["tool"]
};
</script>

<template>
  <div class="modal-container">
    <div class="modal-wrapper card">
      <div class="card-body bt">
        <slot name="body">
          <h4>
            <i class="fa fa-times mr-3"/> Remove tool
          </h4>

          <p>
            Are you sure you want to remove
            <b>{{tool.title}}</b>?
          </p>

          <div class="form-row">
            <div class="col-3 offset-6">
              <button class="btn btn-secondary btn-block" @click="$emit('onCancel')">Cancel</button>
            </div>
            <div class="col-3">
              <button
                class="btn btn-primary btn-block"
                @click="$emit('onConfirm', tool)"
                :disabled="!tool.id"
              >Yes, remove</button>
            </div>
          </div>
        </slot>
      </div>
    </div>
  </div>
</template>
