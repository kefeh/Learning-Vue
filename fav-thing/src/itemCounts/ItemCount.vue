<template>
    <div class="items">
        <span>{{numItems}} items</span>
    </div>
</template>

<script>
export default {
  name: 'ItemCount',
  props: ['numItems'],
}
</script>


<style>
.items {
    color: white;
    font-size: 2vh;
    font-weight: bold;
    background-color: #0b91cb67;
    border-radius: 100px;
    padding: 0 1vw;
    position: absolute;
    right: 4%;
    height: 5vh;
    bottom: 0;
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>


