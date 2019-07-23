<template>
    <div ref="documents" class="col-3-of-4 search-thing-section">
        <NavHeader :title="'Search Results'"/>
        <ul class="search-things" v-if="section == 'FavThing'">
            <li v-for="(thing, index) in getThings" :key="index" :class="[expandThis(index), 'search-list-items', 'row']" :style="nothingToSearch()">
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
                <div class="col-3-of-4 some-grid">
                    <div class="fav-thing-info">
                        <div class="col-3-of-4 some-grid fav-thing" @click="indexToExpand(index)">
                            <span class="fav-title"> {{thing.title}} </span>
                            <span class="fav-description">
                                {{thing.description}}
                            </span>
                            <span class="fav-metadata"> {{thing.metadata}} </span>
                        </div>
                        <div class="col-1-of-4 col-small fav-item">
                            <button class="edit-icon-holder">
                                <svg class="edit-icon">
                                    <use xlink:href="../icons/sprite.svg#icon-pencil"></use>
                                </svg>
                            </button>
                            <span class="time"> {{thing.updated_at}} </span>
                            <svg class="delete-icon">
                                <use xlink:href="../icons/sprite.svg#icon-outline-delete_forever-24px"></use>
                            </svg>
                        </div>
                    </div>
                </div>
            </li>
        </ul>
        <ul class="cat-things" v-if="section == 'Category'">
            <li v-for="(category, index) in getThings" :key="index" class="row cats" onclick="location.href='#';" :style="nothingToSearch()">
                <div class="col-1-of-4 cat-leading">
                    <span class="text">{{category.title}}</span>
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
        <span class="nothingOnSearch" v-if="nothingOnSearch">Nothing Found On Search</span>
        <ItemCount :numItems="numItems" />
    </div>
</template>

<script>
import NavHeader from '../navHeader/NavHeader.vue';
import ItemCount from '../itemCounts/ItemCount.vue';

export default {
  name: 'SearchResults',
  props: ['things', 'section', 'numItems'],
  components: {
    NavHeader,
    ItemCount,
  },
  data() {
    return {
      expandedIndex: -1,
      nothingOnSearch: false,
      expandIndex: -1,
    }
  },
  computed: {
    getThings() {
      if(this.things.length === 1 && this.things[0].title === 'Nothing matched that') {
          this.nothingOnSearch = true;
          this.ItemCount = 0;
      }else{
          this.nothingOnSearch = false;
          this.ItemCount = this.things.length;
      }
      console.log(this.things)
      return this.things;
    }
  },
  methods: {
    nothingToSearch() {
      this.ItemCount = 0;
      return {
          display: this.nothingOnSearch ? 'none' : 'flex'
      };
    },
    indexToExpand(idx) {
      this.expandIndex = this.expandIndex === idx ? -1 : idx;
    },
    expandThis(idx) {
      return this.expandIndex ===  idx ? 'expanded' : 'hovering';
    },
  },
  created: function() {
    if(this.things.length === 1 && this.things[0].title === 'Nothing matched that') {
        this.nothingOnSearch = true;
    }else{
        this.nothingOnSearch = false;
    }
  }
};
</script>


<style>
.search-thing-section {
    position: relative;
}
.nothingOnSearch{
    position: absolute;
    top: 50%;
    left: 40%;
    transform: translateY(-50%);
    color: white;
    font-size: 3vh;
}
.search-things{
    max-height: 70vh;
    overflow-y: auto;
    margin-bottom: 0;
}
.search-list-items{
    color: white;
    border-bottom: 0.1rem solid #0b91cb67;
    min-height: 14vh;
    pointer-events: all;
    cursor: pointer;
}
.hovering:hover .delete-icon {
    display: unset;
}
.hovering:hover .time{
    display: none;
}
.hovering:hover .drag-dots-holder{
    display: flex;
}
.hovering:hover .rank-content{
    margin-left: -2%;
}

/* This is the section I would want to show upon click */
.expanded .fav-metadata, .expanded .created-at-text, .expanded .edit-icon-holder, .expanded .time{
    display: unset;
}
.expanded .edit-icon-holder, .expanded .time{
    margin-right: 20%;
}
.expanded .delete-icon, .expanded .drag-dots-holder {
    display: none;
}
.expanded .fav-description{
    overflow: unset;
    white-space: unset;
    text-overflow: unset;
}
.expanded .rank-content{
    margin-left: unset;
}
.expanded ~ .add-item .btn{
    background-color:  #0b91cb15;
}
.top-nav-item {
    position: relative;
    flex: 1;
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-items: center;
}
.top-nav-item>span{
    margin-top: 15%;
}
.top-nav-item:hover{
    background-color: #0b91cb0a;
}
.indicator {
    background-color: #263049;
    position: absolute;
    bottom: 0;
    width: 90%;
    height: 4%;
    transition-timing-function: ease-out;
}
.showing {
    background-color: #0b91cb !important;
    transition-duration: 700ms;
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
.some-grid {
    display: grid;
}
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
.fav-metadata, .created-at-text, button.edit-icon-holder{
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
</style>
