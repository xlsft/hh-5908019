<script setup lang="ts">
    import Inventory from './components/Inventory.vue';
</script>

<template>
    <main>
        <div class="inventories">
            <Suspense>
                <Inventory entity="user"/>                
            </Suspense>
            <Suspense>
                <Inventory entity="bot"/>
            </Suspense>
        </div>
    </main>
</template>

<style scoped>
    main {
        flex-grow: 1;
        display: flex;
        flex-direction: column;
    }

    .inventories {
        display: flex;
        gap: 12px;
        flex-grow: 1;
        @media screen and (width < 768px) {
            flex-direction: column;
        }
    }
</style>