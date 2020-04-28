<template>
    <div id="maintitle">
      <div class="maintitle">
        <div class="closebtn" @click="testfn('close')">X</div>
        <div class="closebtn" @click="testfn('max')">X</div>
        <div class="closebtn" @click="testfn('min')">X</div>
      </div>
    </div>
</template>

<script>
  const {ipcRenderer: ipc} = require('electron')
  export default {
    name: 'Maintitle',
    methods: {
      testfn: function (e) {
        ipc.send(e)
      }
    }
  }
</script>

<style>
    #maintitle {
        width: 100%;
        height: 52px;
        background-color: #454a60;
        -webkit-app-region: drag;/* 可拖动 */
        position: relative;
    }
    .closebtn{
      z-index: 999999;
      -webkit-app-region: no-drag;/* 可拖动 */
      /* position: absolute; */
      /* left: 0px;
      top: 0px; */
    }
</style>