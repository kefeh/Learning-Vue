<template>
    <div class="col-3-of-4 cat-section">
        <nav class="header cat-header">
            <span class="cat-title">Category</span>
        </nav>
        <ul class="cat-things" v-for="(category, index) in getCategoryList" :key="index">
            <li class="row cats" onclick="location.href='#';">
                <div class="col-1-of-4 cat-leading">
                    <span class="text">{{category.name}}</span>
                    <span class="created-at">Created on {{category.createdAt}}</span>
                </div>
                <div class="col-3-of-4 cat-info">
                    <div class="col-3-of-4 cat-things-info">
                        <span>{{category.numberOfThings}} favorite things</span>
                    </div>
                    <div class="col-1-of-4 cat-right-icons">
                        <svg class="delete-icon" style="display:unset">
                            <use xlink:href="../icons/sprite.svg#icon-outline-delete_forever-24px"></use>
                        </svg>
                        <div style="display: unset">
                            <svg class="edit-icon">
                                <use xlink:href="../icons/sprite.svg#icon-pencil"></use>
                            </svg>
                        </div>
                    </div>
                </div>
            </li>
        </ul>
        <Pagination 
          @newSetGenerated="setDataPaginationValues"
          :startSetNumber="startSetNumber"
          :startIndex="startIndex"
          :currentSetNumber="currentSetNumber"
          :endSetNumber="endSetNumber"
          :itemList="categories"
          :numItems="numItems" />
    </div>
</template>


<script>
import categories from '../data/categories';
import Pagination from '../pagination/PaginationSection.vue'

export default {
  name: 'CategoryContent',
  data() {
    return {
      categories,
      startIndex: 0,
      currentSetNumber: 1,
      startSetNumber: 1,
      endSetNumber: 0,
      numItems: 4,
    };
  },
  components: {
    Pagination,
  },
  computed: {
    getCategoryList() {
      const categoryList = this.categories.slice(this.startIndex, this.startIndex+4);
      return categoryList;
    },
  },
  methods: {
    setDataPaginationValues(startIndex, currentSetNumber) {
      this.startIndex = startIndex;
      this.currentSetNumber = currentSetNumber;
    },
  },
  created: function() {
    let totItems = this.categories.length;
    let firstGroup = totItems % 4;
    if (firstGroup * 4 < totItems){
    this.endSetNumber = firstGroup + 1;
    } else {
    this.endSetNumber = firstGroup;
    }
  },
};
</script>


<style>
.header .cat-header{
    display: flex;
}
.cat-header span{
    margin: auto;
    color: white;
    font-size: 2.5vh;
    font-family: Arial, Helvetica, sans-serif;
}
.cat-right-icons{
    display: flex;
    align-items: center;
    justify-content: space-evenly;
}
.cat-things-info{
    font-size: 3vh;
    font-family: 'Courier New', Courier, monospace;
    color: white;
    display: flex;
}
.cat-things-info span{
    margin: auto;
}
div.cat-info{
    display: flex;
    align-content: center;
    justify-content: space-between;
}
.cat-leading .text{
    border-radius: 0.5rem !important;
    box-shadow: none !important;
    background-color: #0b91cb67;
    padding: 0.4vh 2vw;
    font-size: 3vh;
    color: white;
    font-family: 'Courier New', Courier, monospace;
}
.cat-leading .created-at{
    color: white;
    font-size: 1.5vh;
    font-family: Arial, Helvetica, sans-serif;
}
.cat-leading{
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: space-around;
}
.cats{
    height: 16vh;
    width: 100%;
    border-radius: 2rem;
    border: 0.4vh solid #0b91cb2a;
    padding-left: 2vw;
    margin-top: 2vh !important;
}
.cat-things{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center
}
</style>
