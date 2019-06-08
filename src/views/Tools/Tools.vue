<script>
import Tool from "./Tool";
import ModalAdd from "./ModalAdd";
import ModalRemove from "./ModalRemove";

import ToolService from "../../services/ToolService";

export default {
  components: { Tool, ModalAdd, ModalRemove },
  data() {
    return {
      tools: [],
      tool: {},
      searchText: "",
      isTagsOnly: false,
      showModalAdd: false,
      showModalRemove: false
    };
  },
  computed: {
    filteredTools() {
      return this.tools.filter(
        tool =>
          (!this.isTagsOnly &&
            tool.title.toLowerCase().search(this.searchText.toLowerCase()) !==
              -1) ||
          JSON.stringify(tool.tags)
            .toLowerCase()
            .search(this.searchText.toLowerCase()) !== -1
      );
    }
  },
  mounted() {
    this.fetchTools({});
  },
  methods: {
    async fetchTools(params) {
      this.tools = await ToolService.fetchTools(params);
    },
    async saveTool(params) {
      let newTool = await ToolService.saveTool(params);

      this.searchText = "";
      this.isTagsOnly = false;

      this.fetchTools({});
    },
    async removeTool(params) {
      let newTool = await ToolService.removeTool(params);

      this.searchText = "";
      this.isTagsOnly = false;

      this.fetchTools({});
    },
    async handleAddClick() {
      this.showModalAdd = true;
    },
    async handleModalAddConfirm(tool) {
      this.saveTool({ data: { ...tool, tags: tool.tags.split(" ") } });

      this.showModalAdd = false;
    },
    async handleRemoveClick(tool) {
      this.tool = tool;
      this.showModalRemove = true;
    },
    async handleModalRemoveConfirm(tool) {
      this.removeTool({ id: tool.id });

      this.showModalRemove = false;
    }
  }
};
</script>

<template>
  <div>
    <h3 class="font-weight-bold">Tools</h3>

    <div class="form-row">
      <div class="col-4">
        <input type="text" v-model="searchText" class="form-control" placeholder="search">
      </div>

      <div class="col-4">
        <label class="form-check mt-2">
          <input type="checkbox" v-model="isTagsOnly" class="form-check-input">
          search in tags only
        </label>
      </div>

      <div class="col-2 offset-2">
        <button type="button" class="btn btn-primary btn-block" @click="handleAddClick">
          <i class="fa fa-plus"/> Add
        </button>
      </div>
    </div>

    <tool
      v-for="(tool, index) in filteredTools"
      :key="tool.title + index"
      :tool="tool"
      @onRemoveClick="handleRemoveClick"
    />

    <modal-add
      v-if="showModalAdd"
      @onCancel="showModalAdd = false"
      @onConfirm="handleModalAddConfirm"
    />

    <modal-remove
      v-if="showModalRemove"
      :tool="tool"
      @onCancel="showModalRemove = false"
      @onConfirm="handleModalRemoveConfirm"
    />
  </div>
</template>
