<template>
    <div class="col-3-of-4 cat-section">
        <NavHeader :title="'Categories'"/>
        <ul class="cat-things">
            <li v-for="(category, index) in categories" :key="index" class="row cats">
                <div class="col-1-of-4 cat-leading">
                    <span v-if="!setEdited(index)" class="text">{{category.title}}</span>
                    <form id="inputForm" action="#" v-if="setEdited(index)">
                       <input type="text" class="text cat-edit-input" v-model="input" :placeholder="category.title">
                    </form>
                    <span class="created-at">Created on {{category.createdAt}}</span>
                </div>
                <div class="col-3-of-4 cat-info">
                    <div class="col-3-of-4 cat-things-info" @click="setClickedCategory(category.title)">
                        <span>{{category.numberOfThings}} favorite things</span>
                    </div>
                    <div class="col-1-of-4 cat-right-icons">
                        <svg class="delete-icon" style="display:unset">
                            <use xlink:href="../icons/sprite.svg#icon-outline-delete_forever-24px"></use>
                        </svg>
                        <button v-if="!setEdited(index)" class="cat-edit-icon-holder" style="display: unset" @click="setEditCategory(index)">
                            <svg class="edit-icon">
                                <use xlink:href="../icons/sprite.svg#icon-pencil"></use>
                            </svg>
                        </button>
                        <button form="inputForm" value="submit" class="cat-save" v-if="setEdited(index)" @click="setSave()">
                            Save
                        </button>
                    </div>
                </div>
            </li>
        </ul>
        <div v-if="deletedCategory" class="delete">
            <span>Are you Sure you want to delete {{}} ?</span>
            <button class="noBtn">No<button>
            <button class="yesBtn">Yes</button>
        </div>
        <AddButton/>
        <ItemCount :numItems="numItems" />
    </div>
</template>


<script>
import categories from '../data/categories';
import ItemCount from '../itemCounts/ItemCount.vue';
import AddButton from '../addButton/AddButton.vue';
import NavHeader from '../navHeader/NavHeader.vue';

export default {
  name: 'CategoryContent',
  data() {
    return {
      categories,
      numItems: categories.length,
      editIndex: -1,
      input: '',
      deletedCategory: '',
    };
  },
  components: {
    ItemCount,
    AddButton,
    NavHeader
  },
  methods: {
    setClickedCategory(cat) {
      this.$emit('clickedCategory', cat);
    },
    setEditCategory(index) {
      this.editIndex = index;
    },
    setEdited(index) {
      return this.editIndex === index;
    },
    setSave() {
      console.log(this.input);
      this.editIndex = -1;
    //   TODO: Handle update of the category after the save methode is clicked.
      this.input = '';
    },
    setDelete(category) {
      this.deletedCategory = category;
    },
  },
  created: function() {
    this.$emit('categoriesAvailable', this.categories);
  },
};
</script>


<style>
.cat-edit-icon-holder {
    background: none;
    border: none;
    outline: none;
    padding: 10%;
}
.cat-edit-input {
    color: rgba(255, 255, 255, 0.726);
    width: 70%;
}
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
    /* display: grid; */
    max-height: 72vh;
    overflow-y: auto;
    position: relative;
    margin-bottom: 0;
}
</style>
