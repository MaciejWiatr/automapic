<template>
    <div
        class="text-white text-3xl border p-2 rounded cursor-move w-fit select-none"
        ref="element"
        @mousemove="updateMouseCords"
        @mousedown="startDrag"
        @mouseup="endDrag"
        @mouseleave="endDrag"
        @dblclick="onDoubleClick"
        
        :style="{transform: `translateX(${mouseCords.x}px) translateY(${mouseCords.y}px)`}"
    >

        <p  v-if="!editing">
            {{text}}
        </p>
        <input @dblclick="onDoubleClick" class="text-black" v-else v-model="text">
    </div>
</template>

<script setup>
import { computed, reactive,ref } from 'vue';

const {text} = defineProps({
    text: {
        type: String,
        default: ''
    }
})

const element = ref(null)
const mouseCords = reactive({ x: 0, y: 0 })
const dragging = ref(false)
const editing = ref(false)

const startDrag = () => {
    dragging.value = true
}

const endDrag = () => {
    dragging.value = false
}

const updateMouseCords = (e) =>{
    if(dragging.value === true){
        const editorEl = document.getElementById("editor")
        mouseCords.x = e.clientX - editorEl.getBoundingClientRect().left - element.value.getBoundingClientRect().width /2
        
        mouseCords.y = e.clientY - editorEl.getBoundingClientRect().top - element.value.getBoundingClientRect().height /2

        console.log(element)
    }
}

const onDoubleClick = () => {
    editing.value = !editing.value
}



</script>

<style lang="scss" scoped>
</style>