<template>
    <div class="col-3-of-4 fav-thing-section">
        <nav class="header">
            <ul class="top-nav">
                <li class="top-nav-item" v-for="(category, index) in categories" :key="index">
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
            <li onclick="location.href='#';" class="list-items row">
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
                            <span>01</span>
                        </div>
                    </div>
                    <span class="created-at-text">created at 4th April 2019</span>
                </div>
                <div class="col-3-of-4">
                    <div class="fav-thing-info">
                        <div class="col-3-of-4 fav-thing">
                            <span class="fav-title">Ngoulla Sob Christian</span>
                            <span class="fav-description">Hope you are doing well and hope this finds you well. I am writing
                                to follow up on the email on this thread. Since I responded, I haven't had a reply
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                            </span>
                            <span class="fav-metadata">Some of the metadata that can exist</span>
                        </div>
                        <div class="col-1-of-4 col-small fav-item">
                            <div class="edit-icon-holder">
                                <svg class="edit-icon">
                                    <use xlink:href="../icons/sprite.svg#icon-pencil"></use>
                                </svg>
                            </div>
                            <span class="time">09:54</span>
                            <svg class="delete-icon">
                                <use xlink:href="../icons/sprite.svg#icon-outline-delete_forever-24px"></use>
                            </svg>
                        </div>
                    </div>
                </div>
            </li>
            <li onclick="location.href='#';" class="list-items row">
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
                            <span>01</span>
                        </div>
                    </div>
                    <span class="created-at-text">created at 4th April 2019</span>
                </div>
                <div class="col-3-of-4">
                    <div class="fav-thing-info">
                        <div class="col-3-of-4 fav-thing">
                            <span class="fav-title">Ngoulla Sob Christian</span>
                            <span class="fav-description">Hope you are doing well and hope this finds you well. I am writing
                                to follow up on the email on this thread. Since I responded, I haven't had a reply
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                            </span>
                            <span class="fav-metadata">Some of the metadata that can exist</span>
                        </div>
                        <div class="col-1-of-4 col-small fav-item">
                            <div class="edit-icon-holder">
                                <svg class="edit-icon">
                                    <use xlink:href="../icons/sprite.svg#icon-pencil"></use>
                                </svg>
                            </div>
                            <span class="time">09:54</span>
                            <svg class="delete-icon">
                                <use xlink:href="../icons/sprite.svg#icon-outline-delete_forever-24px"></use>
                            </svg>
                        </div>
                    </div>
                </div>
            </li>
            <li onclick="location.href='#';" class="list-items row">
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
                            <span>01</span>
                        </div>
                    </div>
                    <span class="created-at-text">created at 4th April 2019</span>
                </div>
                <div class="col-3-of-4">
                    <div class="fav-thing-info">
                        <div class="col-3-of-4 fav-thing">
                            <span class="fav-title">Ngoulla Sob Christian</span>
                            <span class="fav-description">Hope you are doing well and hope this finds you well. I am writing
                                to follow up on the email on this thread. Since I responded, I haven't had a reply
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                            </span>
                            <span class="fav-metadata">Some of the metadata that can exist</span>
                        </div>
                        <div class="col-1-of-4 col-small fav-item">
                            <div class="edit-icon-holder">
                                <svg class="edit-icon">
                                    <use xlink:href="../icons/sprite.svg#icon-pencil"></use>
                                </svg>
                            </div>
                            <span class="time">09:54</span>
                            <svg class="delete-icon">
                                <use xlink:href="../icons/sprite.svg#icon-outline-delete_forever-24px"></use>
                            </svg>
                        </div>
                    </div>
                </div>
            </li>
            <li onclick="location.href='#';" class="list-items row">
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
                            <span>01</span>
                        </div>
                    </div>
                    <span class="created-at-text">created at 4th April 2019</span>
                </div>
                <div class="col-3-of-4">
                    <div class="fav-thing-info">
                        <div class="col-3-of-4 fav-thing">
                            <span class="fav-title">Ngoulla Sob Christian</span>
                            <span class="fav-description">Hope you are doing well and hope this finds you well. I am writing
                                to follow up on the email on this thread. Since I responded, I haven't had a reply
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                            </span>
                            <span class="fav-metadata">Some of the metadata that can exist</span>
                        </div>
                        <div class="col-1-of-4 col-small fav-item">
                            <div class="edit-icon-holder">
                                <svg class="edit-icon">
                                    <use xlink:href="../icons/sprite.svg#icon-pencil"></use>
                                </svg>
                            </div>
                            <span class="time">09:54</span>
                            <svg class="delete-icon">
                                <use xlink:href="../icons/sprite.svg#icon-outline-delete_forever-24px"></use>
                            </svg>
                        </div>
                    </div>
                </div>
            </li>
            <li onclick="location.href='#';" class="list-items row">
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
                            <span>01</span>
                        </div>
                    </div>
                    <span class="created-at-text">created at 4th April 2019</span>
                </div>
                <div class="col-3-of-4">
                    <div class="fav-thing-info">
                        <div class="col-3-of-4 fav-thing">
                            <span class="fav-title">Ngoulla Sob Christian</span>
                            <span class="fav-description">Hope you are doing well and hope this finds you well. I am writing
                                to follow up on the email on this thread. Since I responded, I haven't had a reply
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                                I am writing to follow up on the email on this thread. Since I responded, I haven't had a
                                reply from you, I was wondering what next steps would be and how to proceed from here.
                            </span>
                            <span class="fav-metadata">Some of the metadata that can exist</span>
                        </div>
                        <div class="col-1-of-4 col-small fav-item">
                            <div class="edit-icon-holder">
                                <svg class="edit-icon">
                                    <use xlink:href="../icons/sprite.svg#icon-pencil"></use>
                                </svg>
                            </div>
                            <span class="time">09:54</span>
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
    </div>
</template>


<script>
import favoriteThings from '../data/fav-thing';

export default {
  name: 'FavThings',
  data() {
    return {
      favoriteThings,
      categories: Object.keys(favoriteThings),
    };
  },
  computed: {
    categories() {
      return Object.keys(favoriteThings);
    },
  },
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
