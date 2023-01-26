<script lang="ts">
    import * as Threlte from "@threlte/core";
    import * as Three from "three";
    import * as Utils from "three/src/math/MathUtils";
    import App from "$lib/App.svelte";
</script>

<div class="scene">
   <App/>
</div>

<style>
    .scene {
        width: 100%;
        height: 100%;
        position: absolute;
        inset: 0;
        background: radial-gradient(hsl(220 14% 20%), hsl(220 20% 10%));
        background-attachment: fixed;
    }
</style>
