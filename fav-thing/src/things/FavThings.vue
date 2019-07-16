<template>
    <div class="col-3-of-4 fav-thing-section">
        <nav class="header">
            <ul class="top-nav">
                <li
                  class="top-nav-item"
                  v-for="(category, index) in categories"
                  :key="index"
                  @click="selectedCategory(category)">
                    <span>{{category}}</span>
                </li>
            </ul>
            <div class="extend">
                <svg class="extend-icon">
                    <use href="../icons/sprite.svg#icon-baseline-arrow_forward_ios-24px"></use>
                </svg>
            </div>
        </nav>
        <ul class="favorite-things">
            <li v-for="(thing, index) in things" :key="index" onclick="location.href='#';" class="list-items row">
                <div class="drag-dots-holder">
                    <svg class="drag-dots-icon">
                        <use xlink:href="../icons/sprite.svg#icon-dots-three-vertical"></use>
                    </svg>
                    <svg class="drag-dots-icon">
                        <use xlink:href="../icons/sprite.svg#icon-dots-three-vertical"></use>
                    </svg>
                </div>
                <div class="col-1-of-4 col-small rank-content">
                    <div class="rank">
                        <span>Rank</span>
                        <div class="number-holder">
                            <span>{{thing.rank}}</span>
                        </div>
                    </div>
                    <span class="created-at-text">Created on {{thing.created_at}}</span>
                </div>
                <div class="col-3-of-4">
                    <div class="fav-thing-info">
                        <div class="col-3-of-4 fav-thing">
                            <span class="fav-title"> {{thing.title}} </span>
                            <span class="fav-description">
                                {{thing.description}}
                            </span>
                            <span class="fav-metadata"> {{thing.metadata}} </span>
                        </div>
                        <div class="col-1-of-4 col-small fav-item">
                            <div class="edit-icon-holder">
                                <svg class="edit-icon">
                                    <use xlink:href="../icons/sprite.svg#icon-pencil"></use>
                                </svg>
                            </div>
                            <span class="time"> {{thing.updated_at}} </span>
                            <svg class="delete-icon">
                                <use xlink:href="../icons/sprite.svg#icon-outline-delete_forever-24px"></use>
                            </svg>
                        </div>
                    </div>
                </div>
            </li>
        </ul>
        <button class="add-item btn">
            <svg class="add-btn-icon">
                <use xlink:href="../icons/sprite.svg#icon-outline-add-24px"></use>
            </svg>
        </button>
        <ItemCount :numItems="numItems" />
    </div>
</template>


<script>
import favoriteThings from '../data/fav-thing';
import ItemCount from '../itemCounts/ItemCount.vue';

export default {
  name: 'FavThings',
  components: {
    ItemCount,
  },
  data() {
    return {
      favoriteThings,
      things: [],
      numItems: 0,
    };
  },
  computed: {
    categories() {
      return Object.keys(favoriteThings);
    },
  },
  methods: {
    selectedCategory(category) {
      this.things = this.favoriteThings[category];
      this.numItems = this.things.length;
    },
  },
  created: function() {
    this.things = this.favoriteThings.Person;
    this.numItems = this.things.length;
  }
};
</script>


<style>
.favorite-things{
    max-height: 70vh;
    overflow-y: auto;
}
.list-items{
    color: white;
    border-bottom: 0.1rem solid #0b91cb67;
    min-height: 14vh;
    pointer-events: all;
    cursor: pointer;
}
.list-items:hover .delete-icon {
    display: unset;
}
.list-items:hover .time{
    display: none;
}
.list-items:hover .drag-dots-holder{
    display: flex;
}
.list-items:hover .rank-content{
    margin-left: -2%;
}

/* This is the section I would want to show upon click */
.list-items:active .fav-metadata, .list-items:active .created-at-text, .list-items:active .edit-icon-holder, .list-items:active .time{
    display: unset;
}
.list-items:active .edit-icon-holder, .list-items:active .time{
    margin-right: 20%;
}
.list-items:active .delete-icon, .list-items:active .drag-dots-holder {
    display: none;
}
.list-items:active .fav-description{
    overflow: unset;
    white-space: unset;
    text-overflow: unset;
}
.list-items:active .rank-content{
    margin-left: unset;
}
.list-items:active ~ .add-item .btn{
    background-color:  #0b91cb15;
}

/* Rank and content */
.rank-content{
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
    align-self: stretch;
    padding: 2% 0;
}
.rank{
    display: flex;
    align-items: center;
    justify-content: space-between;
    justify-self: center;
    align-self: center;
    background-color:  #263049;
    color: white;
    font-family: Arial, Helvetica, sans-serif;
    border: none;
    outline: none;
    width: 5vw;
    height: 5vh;
    border-radius: 0.3rem;
    padding-left: 0.3rem;
    font-size: 2vh;
}

/* avorite thing details */
.fav-thing-info{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.fav-thing span{
    margin:auto 0;
    padding-top: 2%;
}
.fav-thing span:last-child{
    margin-bottom: 2%;
}
.fav-description, .fav-metadata{
    color: rgba(255, 255, 255, 0.7);
    max-width: 40vw;
    font-size: 1.8vh;
    overflow: hidden;
    text-overflow: ellipsis !important;
    white-space: nowrap;
}
.fav-metadata, .created-at-text, div.edit-icon-holder{
    display: none;
}
.fav-item{
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: flex-end;
    align-self: stretch;
    margin-right: 2%;
}

/* Texts */
.created-at-text{
    position: relative;
    bottom: -25%;
}
.created-at-text{
    font-size: 1.5vh;
}
.fav-title, .time{
    font-size: 2vh;
}

.add-item{
    position: absolute;
    right: 10%;
    bottom: 19%;
}
</style>
