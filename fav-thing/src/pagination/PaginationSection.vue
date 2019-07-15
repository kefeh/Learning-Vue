<template>
    <div class="pagination">
        <div class="pag-button">
            <button class="button" @click="setPrevSet()">
                <svg class="pag-icon">
                    <use href="../icons/sprite.svg#icon-baseline-arrow_back_ios-24px"></use>
                </svg>
            </button>
        </div>
        <span>{{startSetNumber}}</span>
        <span>{{cSetNumber}}</span>
        <span>{{endSetNumber}}</span>
        <div class="pag-button">
            <button class="button" @click="setNextSet()">
                <svg class="pag-icon">
                    <use href="../icons/sprite.svg#icon-baseline-arrow_forward_ios-24px"></use>
                </svg>
            </button>
        </div>
    </div>
</template>

<script>
export default {
  name: 'PaginationSection',
  data() {
    return {
      sIndex: this.startIndex,
      cSetNumber: this.currentSetNumber,
    };
  },
  props: ['itemList', 'startIndex', 'startSetNumber', 'currentSetNumber', 'endSetNumber', 'numItems'],
  methods: {
    setNextSet() {
      let newStartIndex = this.sIndex + this.numItems;
      if (newStartIndex + this.numItems < this.itemList.length) {
          this.sIndex = newStartIndex;
          this.cSetNumber += 1;
      } else {
          if ((this.itemList.length - (this.numItems + 1)) < newStartIndex){
              if (this.sIndex < (this.itemList.length - this.numItems)){
                  this.cSetNumber += 1;
              }
              this.sIndex = this.itemList.length - this.numItems;
          };
      };
      this.$emit('newSetGenerated', this.sIndex, this.cSetNumber);
    },
    setPrevSet() {
      let newStartIndex = this.sIndex - this.numItems;
      if (newStartIndex >= 0) {
          this.sIndex = newStartIndex;
          this.cSetNumber -= 1;
      } else {
          this.sIndex = 0;
          this.cSetNumber = 1;
      };
      this.$emit('newSetGenerated', this.sIndex, this.cSetNumber);
    },
  },
}
</script>


<style>
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


