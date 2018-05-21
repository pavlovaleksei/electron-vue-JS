<template>
  <div>
      <h1>File system</h1>
      <button class="btn btn-default" v-on:click="fileOpen">
        <span class="icon icon-folder"></span>
      </button>
  </div>
</template>

<script>
  const remote = window.require('electron').remote;
  const dialog = remote.dialog;

  export default {
    data () {
      return {
        files: []
      }
    },
    methods: {
      fileOpen (event) {
        let tempPath = dialog.showOpenDialog({
            properties: ['openFile', 'multiSelections']
        });
      }
    }
  }
</script>
