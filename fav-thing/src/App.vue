<template>
  <div id="app">
    <main>
      <HomePage/>
    </main>
  </div>
</template>

<script>
import HomePage from './Home/HomePage.vue';

export default {
  name: 'app',
  components: {
    HomePage,
  },
};
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  list-style-type: none;
}

html, body{
  height: 100%;
  align-content: center;
  background-color: #15182D;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
}


/* Navigations */
.extend{
    width: 5%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
}
/* Header */
.header{
    display: flex;
    width: 100%;
    background-color: #263049;
    height: 10vh;
    justify-items: center;
    justify-content: space-between;
    align-content: center;
}
.top-nav{
    width: 95%;
    height: 100%;
    display: flex;
    justify-items: center;
    justify-content: space-evenly;
    align-content: center;
    color: white;
}
.top-nav .top-nav-item{
    display: flex;
    align-items: center;
    cursor: pointer;
    padding: 2vh 4vw;
}
.top-nav .top-nav-item:focus{
    color: red;
}


/* Components */
/* Search */
.search {
    flex: 0 0 25%;
    display: flex;
    align-items: center;
    justify-content: center;
}
.search-input{
    font-family: Arial, Helvetica, sans-serif;
    color: #a9a9d693;
    border: none;
    padding: 0 4vh;
    height: 5vh;
    border-radius: 100px;
    width: 100%;
    background-color: #0b91cb3a;
    margin-right: -2vw;
    font-size: 2vh;
}
.search-input:focus{
    outline: none;
    width: 100%;
    background-color: #0b91cb3a;
    color: #a9a9d6;
}

.search-button::-moz-focus-inner{
    border: none;
}
.search-button:focus{
    outline: none;
    transform: translateY(2px);
    background-color: #0b91cb;
}
.search-icon:focus, .search-icon:active{
    outline: none;
}

/* Sort */
.sort-button{
    padding: 1vh;
    border-radius: 1vh;
}
.sort-button:focus{
    outline: none;
    transform: translateY(2px);
}
.sort-button::-moz-focus-inner{
    border: none;
}
.sort-icon{
    height: 3vh;
    width: 3vh;
    fill: white;
}

/* Extend */
.extend{
    width: 5%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
}

/* Profile */
.profile{
    display: flex;
    flex-direction: column;
    align-items: center;
    color: white;
}
.profile span{
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1rem;
}
.profile-icon{
    height: 9.5vh;
    width: 5vw;
    fill: rgba(255, 255, 255, 0.7);
}

/* btn icons */
.btn-icon, .extend-icon, .delete-icon{
    width: 4vh;
    height: 4vh;
    fill: rgba(255, 255, 255, 0.8);
}

.edit-icon, .search-icon, .add-btn-icon{
    width: 2.5vh;
    height: 2.5vh;
    fill: rgba(255, 255, 255, 0.8);
}

.delete-icon{
    fill: rgb(182, 14, 42);
    display: none;
}
.drag-dots-icon{
    width: 1vw;
    height: 2vh;
    fill: rgba(255, 255, 255, 0.30);
    cursor: move;
}
.drag-dots-icon:first-child{
    margin-right: -25%;
}
.add-btn-icon{
    width: 3vh;
    height: 3vh;
    fill: rgba(255, 255, 255, 0.8);
}


/* IconHolders */
.drag-dots-holder{
    display: none;
    align-items: center;
    justify-content: center;
    position: relative;
}
/* Profile */
.profile-icon-holder{
    display: flex;
    align-content: unset;
}

.btn-icon-holder{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 35%;
    height: 100%;
    background-color: #0b91cb;
    margin-right: 5%;
    border-radius: 0.8rem;
}

.btn-active .btn-icon-holder{
    background-color: #263049;
    transition-duration: 500ms;
}


.rank-item-holder{
    width: 100%;
    display: flex;
    justify-content: stretch;
    align-items: center;
    flex-direction: column;
    color: white;
}


.edit-icon-holder, .search-button{
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 1.8vh;
    background-color: #0b91cb;
    border-radius: 10rem;
    border: none;
    outline: none;
}

.number-holder{
    background-color: #0b91cb67;
    height: 100%;
    width: 40%;
    border-radius: 0.2rem;
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>
