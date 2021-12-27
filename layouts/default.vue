<template>
    <v-app>
<!--        <v-navigation-drawer app></v-navigation-drawer>-->

        <v-app-bar app color="orange lighten-2">
            <v-toolbar-title>
                <NuxtLink to="/" style="text-decoration: none;" class="white--text">
                    Amami templates
                </NuxtLink>
            </v-toolbar-title>
        </v-app-bar>

        <v-main>
            <v-container>
                <Nuxt />
            </v-container>
        </v-main>

<!--        <v-footer app></v-footer>-->
    </v-app>
</template>

<script>
export default {
}
</script>

<style>
</style>
