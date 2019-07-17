<template>
    <button class="add-item btn">
        <svg class="add-btn-icon">
            <use xlink:href="../icons/sprite.svg#icon-outline-add-24px"></use>
        </svg>
    </button>
</template>

<script>
export default {
    name: 'AddButton',
}
</script>

<style>
.add-item{
    position: absolute;
    right: 10%;
    bottom: 20%;
    border-radius: 10rem;
    padding: 1.8vh;
    border: none;
    outline: none;
    background-color: #0987bd;
    box-shadow: 0.3px 0.1px 0.2rem black;
}
.add-item::-moz-focus-inner{
    border: none;
}
</style>
