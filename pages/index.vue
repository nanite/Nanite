<template>
    <div>
        <div
            class="splash"
            :style="{
                backgroundImage: `linear-gradient(to bottom, rgba(255, 255, 255, 0), rgba(13, 25, 29, 1)), url(/nanite_top.png)`,
            }"
        >
            <Navbar />
        </div>
        <Projects class="container" />
        <Team class="container" />
    </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>

<style scoped>
.container {
    padding: 2rem 5rem 5rem;
}
.splash {
    background-position: top center;
    background-size: auto;
}
</style>
