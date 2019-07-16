<template>
  <div class="hello">
    <section class="container">
        <div class="section-query">
            <form action="#" class="query-item search">
                <input type="text" class="search-input" placeholder="Search favorite things">
                <button class="search-button">
                    <svg class="search-icon">
                        <!-- <use xlink:href="icons/sprite.svg#icon-magnifying-glass"></use> -->
                        <use xlink:href="../icons/sprite.svg#icon-baseline-search-24px"></use>
                    </svg>
                </button>
            </form>
            <button class="query-item sort-button btn">
                <span>Sort By</span>
                <svg class="sort-icon">
                    <use xlink:href="icons/sprite.svg#icon-outline-expand_more-24px"></use>
                </svg>
            </button>
        </div>
        <div class="row">
            <SectionSide @catClick='setCategoryOption' @favClick='setFavThingOption'/>
            <div class="horizontal-gutter"></div>
            <CategoriesContent v-if="showCategories" />
            <FavThings v-if="showFavThings"/>
        </div>
    </section>
  </div>
</template>

<script>
import SectionSide from '../sideSection/SectionSide.vue';
import CategoriesContent from '../categories/CategoriesContent.vue';
import FavThings from '../things/FavThings.vue';

export default {
  name: 'HomePage',
  data() {
    return {
      showFavThings: true,
      showCategories: false,
    };
  },
  components: {
    SectionSide,
    CategoriesContent,
    FavThings,
  },
  methods: {
    setCategoryOption() {
      this.showCategories = true;
      this.showFavThings = false;
    },
    setFavThingOption() {
      this.showFavThings = true;
      this.showCategories = false;
    },
  },
  props: {
    msg: String,
  },
};
</script>


<style>
section.container {
    max-width: 114rem;
    height: 92vh;
    padding: 2% 4%;
}
.row{
    width: 100%;
    margin: 0 auto;
    display: flex;
}
.col-1-of-4{
    width: 22%;
}
.col-small{
    width: 18%;
}
.col-3-of-4{
    flex: 1;
    display: grid;
}
.horizontal-gutter{
    width: 1%;
}

.card {
    background-color: #263049;
    align-content: center;
    border-radius: 1rem;
}
.card:not(.section-side){
    box-shadow: 0.3px 0.05px 0.2rem #161b2b;
}

.section-query{
    display: flex;
    flex-direction: row-reverse;
    align-items: center;
    margin-bottom: 1%;
}
.query-item{
    margin-left: 1vw;
}

/* btn */
.btn{
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #0b91cb;
    color: white;
    font-family: Arial, Helvetica, sans-serif;
    border: none;
    outline: none;
    transition-timing-function: cubic-bezier(.39,.58,.57,1);
}
.nav-btn{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    align-self: stretch;
}
/* Primary btn */
.primary{
    display: flex;
    width: 60%;
    justify-content: stretch;
    margin-bottom: 1vh;
    border-radius: 1rem;
    background-color: #263049;
    box-shadow: 0.3px 0.05px 0.2rem #161b2b;
}
.primary:first-child{
    margin-bottom: 4vh;
    margin-top: 5%;
}
.btn-active{
    outline: none;
    border: none;
    background-color: #0b91cb;
    transition-duration: 500ms;
}
.btn-active::-moz-focus-inner{
    border: none;
}
.btn-text{
    display: flex;
    align-self: left;
    font-size: 2vh;
    padding: 2.1vh 0;
}


</style>
