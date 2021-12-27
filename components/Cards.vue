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

        <v-card-text>
            <v-row no-gutters>
                <v-col v-for="element in elements" :key="element.algorithm" cols="12">
                    ・
                    <NuxtLink :to="element.link" style="text-decoration: none;" class="light-blue--text">
                        {{ element.algorithm }}
                    </NuxtLink>
                </v-col>
            </v-row>
        </v-card-text>

<!--        <v-card-actions>-->
<!--            <NuxtLink to="/math/GCD_LCM" style="text-decoration: none">-->
<!--                <v-btn color="orange" text>GCD, LCM</v-btn>-->
<!--            </NuxtLink>-->
<!--            <NuxtLink to="/math/Prime-factor" style="text-decoration: none">-->
<!--                <v-btn color="orange" text>Prime factor</v-btn>-->
<!--            </NuxtLink>-->
<!--        </v-card-actions>-->
    </v-card>
</template>

<script>
export default {
    props: [
        "image",
        "category",
        "elements"
    ]
}
</script>

<style>
p {
    font-family: 'Noto Sans', 'Noto Sans JP', sans-serif;
}
</style>
