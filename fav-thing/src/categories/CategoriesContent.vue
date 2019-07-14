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
        <div class="pagination">
            <div class="pag-button">
                <button class="button" @click="setPrevCategorySet()">
                    <svg class="pag-icon">
                        <use href="../icons/sprite.svg#icon-baseline-arrow_back_ios-24px"></use>
                    </svg>
                </button>
            </div>
            <span>{{startSetNumber}}</span>
            <span>{{currentSetNumber}}</span>
            <span>{{endSetNumber}}</span>
            <div class="pag-button">
                <button class="button" @click="setNextCategorySet()">
                    <svg class="pag-icon">
                        <use href="../icons/sprite.svg#icon-baseline-arrow_forward_ios-24px"></use>
                    </svg>
                </button>
            </div>
        </div>
    </div>
</template>


<script>
import categories from '../data/categories';

export default {
  name: 'CategoryContent',
  data() {
    return {
      categories,
      startIndex: 0,
      currentSetNumber: 1,
      startSetNumber: 1,
      endSetNumber: 0,
    };
  },
  computed: {
    getCategoryList() {
      const categoryList = this.categories.slice(this.startIndex, this.startIndex+4);
      return categoryList;
    },
  },
  methods: {
    setNextCategorySet() {
      let newStartIndex = this.startIndex + 4;
      if (newStartIndex + 4 < this.categories.length) {
          this.startIndex = newStartIndex;
          this.currentSetNumber += 1;
      } else {
          if (this.categories.length - 5 < newStartIndex){
              if (this.startIndex < (this.categories.length - 4)){
                  this.currentSetNumber += 1;
              }
              this.startIndex = this.categories.length - 4;
          };
      };
    },
    setPrevCategorySet() {
      let newStartIndex = this.startIndex - 4;
      if (newStartIndex >= 0) {
          this.startIndex = newStartIndex;
          this.currentSetNumber -= 1;
      } else {
          this.startIndex = 0;
          this.currentSetNumber = 1;
      };
    },
  },
  created: function() {
      let totCategories = this.categories.length;
      let firstGroup = totCategories % 4;
      if (firstGroup * 4 < totCategories){
        this.endSetNumber = firstGroup + 1;
      } else {
        this.endSetNumber = firstGroup;
      }
    }
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

/* The Pagination */
.pag-icon {
    width: 2vw;
    height: 3vh;
    fill: white;
}
.button{
    background-color: inherit;
    border: none;
    outline: none;
    border-radius: 100px;
    cursor: pointer;
}
.pagination {
    color: white;
    font-size: 2vh;
    font-weight: bold;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: #0b91cb67;
    border-radius: 100px;
    width: 30%;
    position: relative;
    left: 70%;
    height: 5vh;
    margin-top: 2%;
    padding: 0 1%;
}
.pagination>span:nth-of-type(2) {
    background-color: #0b91cb;
    padding: 2% 4%;
    border-radius: 100px;
}
</style>
