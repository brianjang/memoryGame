<template>
  <div class="board">
    <span>남은 카드</span>
    <h2>{{ nonMatchedPairs }}</h2>
  </div>
</template>

<script lang="ts">
import { defineComponent, computed } from 'vue'
import { useStore } from 'vuex'
import { GameStoreKey } from '@/stores'

export default defineComponent({
  name: 'Progress',
  setup: () => {
    const { state } = useStore(GameStoreKey)
    return {
      nonMatchedPairs: computed(() => state.nonMatchedPairs)
    }
  }
})
</script>

<style scoped>
.board {
  width: 120px;
  height: 100px;
  padding: 10px;
  background-color: #bbada0;
  border-radius: 5px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  color: #eae0d1;
}

span {
  font-size: 19px;
  font-weight: bold;
  display: block;
  width: 100%;
  text-align: center;
}

h2 {
  color: #fff;
}
@media screen and (max-width: 450px) {
  .board {
    width: 105px;
  }
  span {
    font-size: 17px;
  }
}

@media screen and (max-width: 380px) {
  .board {
    width: 95px;
  }
}

@media screen and (max-width: 360px) {
  .board {
    width: 90px;
  }
  span {
    font-size: 15px;
  }
}
</style>
