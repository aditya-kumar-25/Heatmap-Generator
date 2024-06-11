<template>
    <input class="input-grid" :class="[active === 1 ? 'active' : '']" type="number" min="0" max="100"
        v-model="gridValue" @input="setData(index, gridValue)">
</template>


<script>

export default {
    components: {

    },
    props: ['index', 'setData', 'active' , 'num'],
    data() {
        return {
            gridValue: this.num || 0,
        }
    },
}

</script>

<style scoped>
.input-grid {
    text-align: center;
    aspect-ratio: 1;
    border-radius: 20px;
    font-size: x-large;
    background: linear-gradient(to right, #e7ecf1, #ffffff);
    transition: all linear 100ms;
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
}

.input-grid:hover {
    background: radial-gradient(circle at 10% 20%, rgb(7, 121, 222) 0%, rgb(20, 72, 140) 90%);
    color: white;
}

.active {
    background: radial-gradient(circle at 10% 20%, rgb(7, 121, 222) 0%, rgb(20, 72, 140) 90%);
    color: white;
}
</style>