<template>
    <section class="hero is-success is-fullheight">
        <Particle />
        <div class="hero-body">
            <div class="container">
                <h1 class="title has-text-centered">Asteroids</h1>
                <h3 class="subtitle has-text-centered">(Simple Search Engine for Asteroids)</h3>
            </div>
        </div>
</section>
</template>

<script>
import Particle from './particle';
export default {
    name: "Header",
    components:{
        Particle
    }

}
</script>

<style>

</style>