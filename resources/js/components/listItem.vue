<template>
    <div class="item">
        <input
            type="checkbox"
            @change="updateChecked"
            v-model="item.completed"
        />
        {{ item.name }}
        <button @click="removeItem" class="trashcan">
            <font-awesome-icon icon="trash" />
        </button>
    </div>
</template>

<script>
export default {
    props: ["item"],
};
</script>
<style scoped>
.completed {
    text-decoration: line-through;
    color: #999999;
}
.itemText {
    width: 100%;
    margin-left: 20px;
}
.item {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.trashcan {
    background: #e5e5e5;
    border: none;
    color: #ff0000;
    outline: none;
}
</style>
