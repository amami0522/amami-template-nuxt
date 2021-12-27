<template>
    <v-container>
        <v-row justify="center">
            <v-col sm="6" v-for="item in items" :key="item.category">
                <Cards
                    :category="item.category"
                    :image="item.image"
                    :elements="item.elements"
                ></Cards>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import Cards from "./Cards";
import itemsJson from "../assets/algorithms.json"

export default {
    components: {
        Cards
    },
    data() {
        return {
            items: itemsJson
        }
    }
}
</script>
