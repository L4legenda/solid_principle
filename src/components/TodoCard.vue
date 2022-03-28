<template>
    <div class="todo-list__task">
        <span>{{ todo.title }}</span>
    </div>
</template>
<script lang="ts" setup>
import { ITodo } from '@/types'
import {PropType} from "vue";

const props = defineProps({
    todo: {
        required: true,
        type: Object as PropType<ITodo>
    }
})
</script>