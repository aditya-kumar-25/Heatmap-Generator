<template>

    <div>
        <h1>Enter input data</h1>
        <p class="secondary-text">Enter input data to each cell below between <strong>0-100</strong></p>
        <div class="input-data-container">
            <InputGrid v-for="(num , index) in data" :index="index" :key="index" :setData="setData" :active="hovered[index]" :num="num" />
        </div>
    </div>

</template>

<script>
import InputGrid from './InputGrid.vue';

    export default{
        components:{
            InputGrid,
        },
        props: ['data' , 'setData' , 'hovered'],
    }

</script>

<style>
.input-data-container{
    margin-top:50px;
    margin-inline:auto;
    padding: 1rem;
    display:grid;
    grid-template-columns: repeat(3, 1fr);
    width: 80%;
    column-gap:1rem;
    row-gap: 1rem;
    /* border-right: 2px solid gray; */
}

.generate-button{
    margin-top: 20px;
}

</style>