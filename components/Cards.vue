<template>
    <v-card max-width="600">
        <v-img
            :src="image"
            class="white--text align-end"
            height="300px"
        >
            <v-card-title>
                {{ category }}
            </v-card-title>
        </v-img>
    </v-card>
</template>

<script>
export default {
    props: [
        "image",
        "category"
    ]
}
</script>
