<script>
export default {
  props: ["tool"]
};
</script>

<template>
  <div class="card my-3">
    <div class="card-body">
      <a :href="tool.link" target="blank">
        <h4>{{tool.title}}</h4>
      </a>

      <p>{{tool.description}}</p>
      <div class="form-row">
        <div class="col-10">
          <span
            v-for="tag in tool.tags"
            :key="tag"
            class="badge badge-pill badge-light mr-2"
          >#{{tag}}</span>
        </div>

        <div class="col-2">
          <button
            class="btn btn-sm btn-outline-danger btn-block"
            @click="$emit('onRemoveClick', tool)"
          >
            <i class="fa fa-times"/> Remove
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
