<template>
    <div class="GroceryListContainer">
        <div class="heading">
            <h2 id="title">Grocery List</h2>
            <add-item-form />
        </div>
        <list-view :items="items" />
    </div>
</template>
<script>
import axios from "axios";
import addItemForm from "./addItemForm.vue";
import listView from "./listView.vue";
export default {
    components: {
        addItemForm,
        listView,
    },
    data() {
        return {
            items: {},
        };
    },
    methods: {
        getList() {
            axios
                .get("api/items")
                .then((response) => {
                    this.items = response.data;
                })
                .catch((error) => {
                    console.log(error);
                });
            console.log(this.items);
        },
    },
    created() {
        this.getList();
    },
};
</script>

<style scoped>
.GroceryListContainer {
    width: 350px;
    margin: auto;
}
.heading {
    background: #e6e6e6;
    padding: 10px;
}
#title {
    text-align: center;
}
</style>
