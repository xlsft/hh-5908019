<script setup lang="ts">
    import { useStatic } from '../composables/useStatic';
    import type { Item } from '../types/item.types';

    const props = defineProps<{
        entity: 'user' | 'bot'
    }>()

    const data = await useStatic<Item>(`${props.entity}.inventory`)
</script>

<template>
    <div class="inventory" :data-entity="props.entity">
        {{ data }}
    </div>
</template>

<style scoped>
    h2 {
        position: absolute;
        left: 12px;
    }

    .inventory {
        position: relative;
        flex-grow: 1;
        display: grid;
        padding: 12px;
        border-radius: 12px;
        border: 1px #EFEFEF solid;
        grid-template-columns: repeat(4, 1fr);
    }
</style>