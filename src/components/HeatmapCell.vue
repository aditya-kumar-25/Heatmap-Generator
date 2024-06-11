<template>
    <div class="heatmap-cell" :style="cellStyle" @mouseenter="flag = true" @mouseleave="flag = false">
        <div class="tooltip" :class="[`${flag && 'swipe-up'}`]">
            <p>{{ data }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: ['data'],
    data() {
        return {
            flag: false,
        }
    },
    computed: {
        cellStyle() {
            const greenIntensity = Math.floor((this.data / 100) * 255);
            const gradient = `linear-gradient(to bottom, rgba( ${250 - greenIntensity}, 250,  ${250 - greenIntensity} , 0.5), rgb( ${250 - greenIntensity}, 250,  ${250 - greenIntensity}))`;
            return {
                backgroundImage: gradient,
                display: 'flex',
                alignItems: 'center',
                justifyContent: 'center',
                height: '100%',
                width: '100%',
            };
        }
    },
}
</script>


<style scoped>
.heatmap-cell {
    overflow: hidden;
    aspect-ratio: 1;
    border: 1px solid #ccc;
    text-align: center;
    font-size: 1rem;
    min-width: 5px;
    min-height: 5px;
    border-radius: 20px;
    box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
    position: relative;
}

.tooltip {
    position: absolute;
    transform: translateY(100%);
    width: 100%;
    height: 100%;
    /* background: linear-gradient(to top right , #dcccff , #853ee8); */
    background-color: red;
    top: 0;
    left: 0;
    z-index: 10;
    transition: all linear 300ms;
    border-radius: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    font-size: large;
}

.swipe-up {
    transform: translateY(0);
}

.heatmap-cell:hover{
    cursor: pointer;
}

</style>
