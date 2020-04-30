<template>
    <div id="maintitle">
      <div class="maintitle-console">
        <div class="closebtn" @click="testfn('min')">-</div>
        <div class="closebtn iconfont" @click="testfn('max')">&#xe667;</div>
        <div class="closebtn iconfont" @click="testfn('close')">&#xe747;</div>
      </div>
    </div>
</template>

<script>
  const {ipcRenderer: ipc} = require('electron')
  export default {
    data () {
      return {
        ismax: 'max'
      }
    },
    name: 'Maintitle',
    methods: {
      testfn: function (e) {
        ipc.send(e)
        if (e === 'max') {
          data.ismax = 'small'
        }
      }
    }
  }
</script>

<style>
    #maintitle {
        width: 100%;
        height: 52px;
        background-color: #212633;
        -webkit-app-region: drag;/* 可拖动 */
        position: relative;
    }
    .maintitle-console{
      position: absolute; 
      right: 0px;
      top: 0px;
      -webkit-app-region: no-drag;
    }
    .closebtn{
      display: inline-block;
      width: 20px;
      height: 20px;
      background: #454a60;
      color: #c5cde7;
      line-height: 20px;
      text-align: center;
    }
</style>