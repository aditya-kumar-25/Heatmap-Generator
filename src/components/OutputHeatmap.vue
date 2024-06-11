<template>
    <div class="output-container">

        <h1>Heatmap</h1>
        <p class="secondary-text"> Below is the generated heatmap for given input</p>

        <div class="heatmap-container" >
            <HeatmapCell v-for="(num, index) in data" :data="num" :key="index" :index="index"  @mouseenter="updateHovered(index , 1)" @mouseleave="updateHovered(index , 0)" />
        </div>

    </div>
</template>


<script>

import HeatmapCell from './HeatmapCell.vue'

export default {
    components: {
        HeatmapCell,
    },
    props: ['data' , 'updateHovered'],
}
</script>

<style scoped>
.output-container {
    margin-inline: auto;
    min-height: 100vh;
    width: 100%;
}

.heatmap-container {
    margin-inline: auto;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: .5rem;
    width: 80%;
    padding: 50px;
    /* border-left: 2px solid gray; */
}

@media screen and (max-width: 768px) {
    .heatmap-container {
        margin-inline: auto;
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: .5rem;
        width: 90%;
        margin-top: 30px;
        padding: 10px;
        border-left:none;
    }

    .output-container {
    margin-inline: auto;
    min-height: 100vh;
    width:90vw;
}

}
</style>