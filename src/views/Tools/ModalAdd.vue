<script>
export default {
  data() {
    return {
      tool: {
        title: "",
        link: "",
        description: "",
        tags: ""
      }
    };
  }
};
</script>

<template>
  <div class="modal-container">
    <div class="modal-wrapper card">
      <div class="card-body bt">
        <slot name="body">
          <h4>
            <i class="fa fa-plus mr-3"/> Add new tool
          </h4>

          <div class="form-row">
            <div class="col-12">
              <div class="form-group">
                <label>Tool name</label>
                <input type="text" v-model="tool.title" class="form-control">
              </div>
            </div>

            <div class="col-12">
              <div class="form-group">
                <label>Tool link</label>
                <input type="text" v-model="tool.link" class="form-control">
              </div>
            </div>

            <div class="col-12">
              <div class="form-group">
                <label>Tool description</label>
                <textarea v-model="tool.description" class="form-control"/>
              </div>
            </div>

            <div class="col-12">
              <div class="form-group">
                <label>Tags</label>
                <input type="text" v-model="tool.tags" class="form-control">
              </div>
            </div>
          </div>

          <div class="form-row">
            <div class="col-3 offset-6">
              <button class="btn btn-secondary btn-block" @click="$emit('onCancel')">Cancel</button>
            </div>
            <div class="col-3">
              <button
                class="btn btn-primary btn-block"
                @click="$emit('onConfirm', tool)"
                :disabled="!tool.title || !tool.link || !tool.description"
              >Add tool</button>
            </div>
          </div>
        </slot>
      </div>
    </div>
  </div>
</template>
