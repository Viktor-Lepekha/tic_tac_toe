<template>
  <div class="field">
  
    <div
    class="tile"
    v-bind:class="{
      checked: isChecked,
      red: tile.color === 'red',
      yellow: tile.color === 'yellow'
    }"
    :winner="this.winner"
    v-on:click="selectTile"
    v-for="tile in this.tiles"
    :key="tile.id"
    :playersColor="this.playersColor"
    :id="tile.id"
    :isChecked="tile.isChecked"
    >
    </div>
    <h3 v-if="winner">{{this.winner}} has won the game!</h3>
    <h3 v-if="isDraw">It's a draw!</h3>
  </div>
</template>

<script>
// import Tile from './Tile.vue'
export default {
  name: 'Field',
  props: ['playersColor', 'botColor'],
  data() {
    return {
      tiles: Array(9).fill().map((tile, index) => {
        tile = {
          id: index,
          isChecked: false,
          color: 'white',
          value: ''
        }

        return tile
        }),
      winner: '',
      isDraw: false,
    }
  },
  methods: {
    selectTile: function(event) {
      const selectedTile = event.target.id
      if (this.tiles[selectedTile].isChecked === true) {
        alert('This tile has laready been used, choose another one')
      } else {
        this.tiles[selectedTile].isChecked = true;
        this.tiles[selectedTile].color = this.playersColor;
        this.tiles[selectedTile].value = "user";
        setTimeout(this.makeBotMove, 500);
      }
          
    },

    makeBotMove: function() {
      if (this.tiles.some(tile => tile.isChecked === false)) {
         const tileToCheck = Math.floor(Math.random() * 9);
      if (this.tiles[tileToCheck].isChecked === true) {
        this.makeBotMove()
      } else {
        this.tiles[tileToCheck].isChecked = true;
        this.tiles[tileToCheck].color = this.botColor;
        this.tiles[tileToCheck].value = "bot";
        this.calculateWinner(this.tiles)
      }
      } else {
        return
      }      
    },

    calculateWinner: function(tiles) {
      const lines = [
      [0, 1, 2],
      [3, 4, 5],
      [6, 7, 8],
      [0, 3, 6],
      [1, 4, 7],
      [2, 5, 8],
      [0, 4, 8],
      [2, 4, 6],
      ];
      for (let i = 0; i < lines.length; i++) {
        const [a, b, c] = lines[i];
        if (tiles[a].value && tiles[a].value === tiles[b].value && tiles[a].value === tiles[c].value) {
          this.winner = tiles[a].value;
        } 
      }
      return;
      } 
  
  },
  // components: {
  //   Tile
  // }
}
</script>

<style>
.field {
  display: flex;
  flex-wrap: wrap;
  margin: 0 auto;
  width: 330px;
  gap: 10px;
}
.tile {
  width: 100px;
  height: 100px;
  border: 1px solid black;
}

.red {
  background-color: red;
}

.yellow {
  background-color: yellow;
}
</style>