<template>
    <div class="container">
        <div class="todo-list">
            <slot />
            
        </div>
    </div>
</template>
<script lang="ts" setup>
import { PropType } from "vue";
import { ITodo } from '@/types'

const props = defineProps({
    todos: {
        type: Object as PropType<ITodo[]>,
        required: true,
        default: () => []
    },
})
</script>