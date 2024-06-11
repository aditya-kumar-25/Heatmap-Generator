<template>
    <div class="navbar-container">
        <div class="logo">
            <img src="logo.png" height="70px" />
            <h1>Heatmap Generator</h1>
        </div>
    </div>

</template>

<script>
export default {

}
</script>

<style>
.logo {
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0 2px 2px -2px rgba(0, 0, 0, .2);
}

.navbar-container {
    position: fixed;
    background-color: white;
    top: 0;
    left: 0;
    right: 0;
    z-index: 20;
}
</style>