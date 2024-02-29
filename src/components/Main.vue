<template>
  <div id="main">
    <div id="screen">
      <textarea id="screenTextArea"></textarea>
    </div>
    <div id="leftTable">
      <Watch/>
    </div>
    <div id="keyboard">
      <Keyboard/>
    </div>
  </div>
</template>

<script>
import Keyboard from './Keyboard.vue'
import Watch from './Watch.vue'

export default {
  name: 'Main',
  components: {
    Watch, Keyboard
  }
}
</script>

<style scoped>
#main {
  width: 100px;
  height: 100px;
}
#main #screen {
  margin-top: 50px;
  width: 800px;
  height: 350px;
  position: absolute;
  top: 0%;
  left: 50%;
  transform: translate(-50%, -0%);
}
#main #screen #screenTextArea{
  width: 100%;
  height: 100%;
  overflow: auto;
  outline: none;
  border: 4px solid #51557E;
  -webkit-box-shadow: none;
  -moz-box-shadow: none;
  box-shadow: none;
  resize: none;
  color:green;
  background-color: black;
}
#main #screen #screenTextArea::-webkit-scrollbar {
    display: none;
}
#main #leftTable {
  position: absolute;
  top: 80%;
  left: 10%;
  transform: translate(-10%, -80%);
}
#main #keyboard {
  width: 810px;
  height: 300px;
  position: absolute;
  top: 100%;
  left: 50%;
  transform: translate(-50%, -100%);
  background-color: #b6b6b6;
  border: 10px solid transparent;
  border-top-color: #d1d2d7;
  border-left-color: #aaa6a6;
  border-right-color: #9a9ba1;
  border-bottom-color: #757374;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
