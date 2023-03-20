<template>
    <div v-for="item in items">
        <list-item :item="item" class="item" :key="item.id" />
    </div>
</template>

<script>
import listItem from "./listItem.vue";
export default {
    props: ["items"],
    components: {
        listItem,
    },
};
</script>
<style scoped>
.item {
    background: #e6e6e6;
    padding: 5px;
    margin-top: 5px;
}
</style>
