<template>
    <div>
        <ul class="favorite-things">
            <li v-for="(thing, index) in things" :key="index" :class="[expandThis(index), 'list-items', 'row']">
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
    </div>
</template>

<script>
import NavHeader from '../navHeader/NavHeader.vue';

export default {
  name: 'SearchResults',
}
</script>
