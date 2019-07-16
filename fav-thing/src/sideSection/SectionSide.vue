<template>
    <div class="col-1-of-4">
        <div class="card section-side">
            <div class="profile">
                <svg class="profile-icon">
                    <use xlink:href="../icons/sprite.svg#icon-outline-account"></use>
                </svg>
                <span>PROFILE NAME</span>
            </div>
            <div class="side-nav nav-btn">
                <button class="add-new btn primary"  @click="addItemClick()" :class="{'btn-active': showAddItem}">
                    <div class="btn-icon-holder icon-box">
                        <svg class="add-new-icon btn-icon">
                            <use xlink:href="../icons/sprite.svg#icon-outline-add-24px"></use>
                        </svg>
                    </div>
                    <span class="btn-text">Add New</span>
                </button>
                <button class="add-new btn primary" @click="favThingClick()" :class="{'btn-active': showThing}">
                    <div class="btn-icon-holder icon-box">
                        <svg class="add-new-icon btn-icon">
                            <use xlink:href="../icons/sprite.svg#icon-outline-nature_people-24px"></use>
                        </svg>
                    </div>
                    <span class="btn-text">Fav Things</span>
                </button>
                <button  class="add-new btn primary" @click="categoryClick()" :class="{'btn-active': showCategory}">
                    <div class="btn-icon-holder icon-box">
                        <svg class="cat-icon btn-icon">
                            <use xlink:href="../icons/sprite.svg#icon-outline-category-24px"></use>
                        </svg>
                    </div>
                    <span class="btn-text">Categories</span>
                </button>
                <button class="add-new btn primary" @click="auditLogClick()" :class="{'btn-active': showLogs}">
                    <div class="btn-icon-holder icon-box">
                        <svg class="audit-icon btn-icon">
                            <use xlink:href="../icons/sprite.svg#icon-outline-assessment-24px"></use>
                        </svg>
                    </div>
                    <span class="btn-text">Audit Logs</span>
                </button>
            </div>
            <div class="rank-element side-item">
                <h3 class="rank-text">Top Ranked</h3>
                <ol class="rank-item-holder">
                    <li class="rank-items card">
                        <span class="item">Christian Sob Asnel</span>
                        <div class="card category">
                            <span class="cat-text">Person</span>
                        </div>
                    </li>
                    <li class="rank-items card">
                        <span class="item">Christian Sob Asnel</span>
                        <div class="card category">
                            <span class="cat-text">Person</span>
                        </div>
                    </li>
                    <li class="rank-items card">
                        <span class="item">Christian Sob Asnel</span>
                        <div class="card category">
                            <span class="cat-text">Person</span>
                        </div>
                    </li>
                </ol>
            </div>
        </div>
    </div>
</template>


<script>
export default {
  name: 'SectionSide',
  data() {
    return {
      showCategory: false,
      showThing: true,
      showLogs: false,
      showAddItem: false
    };
  },
  methods: {
    setClickedButton({showCategory = false, showThing = false, showLogs = false, showAddItem = false}) {
      this.showCategory = showCategory;
      this.showThing = showThing;
      this.showLogs = showLogs;
      this.showAddItem = showAddItem;
    },
    addItemClick() {
      this.setClickedButton({showAddItem: true});
      this.$emit('showAddItem');
    },
    favThingClick() {
      this.setClickedButton({showThing: true});
      this.$emit('favClick');
    },
    categoryClick() {
      this.setClickedButton({showCategory: true});
      this.$emit('catClick');
    },
    auditLogClick() {
      this.setClickedButton({showLogs: true});
      this.$emit('auditLogClick');
    },
  },
};
</script>


<style>
.section-side {
    height: 80vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    padding: 10% 0;
}

.item{
    padding: 0 1vw;
    line-height: 4vh;
    font-size: 2vh;
}
.category{
    position: absolute;
    bottom: 0;
    right: 0;
    border-radius: 0.5rem !important;
    box-shadow: none !important;
    background-color: #0b91cb67 !important;
}

/* Ranks */
.rank-items{
    height: 9vh;
    width: 18vw;
    margin-bottom: 1vh;
    position: relative;
}
.cat-text{
    padding: 0 2vw;
    line-height: 4vh;
    font-size: 2vh;
}
.rank-text{
    color: white;
    margin-bottom: 0.6vh;
    font-size: 2vh;
}

/* add btn */
.add-item{
    position: absolute;
    right: 10%;
    bottom: 18%;
    border-radius: 10rem;
    padding: 1.8vh;
    border: none;
    outline: none;
    background-color: #0987bd;
    box-shadow: 0.3px 0.1px 0.2rem black;
}
.add-item::-moz-focus-inner{
    border: none;
}
</style>
