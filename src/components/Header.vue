<template>
    <header class="header">
        <div class="container">
            <h1>{{ props.listName }}</h1>
        </div>
    </header>
</template>
<script lang="ts" setup>
const props = defineProps({
  listName: { type: String, required: true },
});

</script>
<style>
#app{
    background-color: #fff;
}
</style>