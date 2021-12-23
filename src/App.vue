
<template>
  <div class="h-screen w-full bg-gray-900 flex items-center justify-center text-white">
    <div class="bg-gray-800 rounded-lg w-5/6 max-w-4xl flex flex-col overflow-hidden">
      <div class="h-96 bg-gray-800 border-b border-gray-700 w-full flex justify-center items-center">
        <Editor/>
      </div>
      <div class="h-80 flex w-full ">
        <div class="flex flex-col w-1/3 text-left p-4">
          <h2 class="pt-2 pb-2 font-semibold" >Elements</h2>
          <ul class="flex flex-col text-sm">
            <li class="bg-gray-700 p-3 rounded flex justify-between items-center">
              <div class="text-gray-400">Text</div>
              <TrashIcon/>
            </li>
          </ul>
        </div>
        <div class="flex flex-col w-1/3 text-left p-4">
          <h2>Options</h2>
          <ul>

          </ul>
        </div>
        <div class="flex flex-col w-1/3 text-left p-4">
          <h2>Custom CSS</h2>
          <ul>

          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TrashIcon from './components/TrashIcon.vue';
import Editor from './components/Editor.vue';
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
