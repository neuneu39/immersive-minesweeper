<template>
  <div id="app">
    <button
      class="start-game"
      v-on:click="gameStart"
      
    >
    Start game
    </button>
    <table 
      class="minesweeper"
      v-if="started"    
    >
      <tr>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
      </tr>
      <tr>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
      </tr>
      <tr>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
      </tr>
      <tr>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
      </tr>
      <tr>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
      </tr>
      <tr>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
      </tr>
      <tr>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
      </tr>
      <tr>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
      </tr>
      <tr>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
      </tr>
      <tr>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
        <td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td><td class="unopened"></td>
      </tr>
    </table> 
  </div>
</template>

<script>
//import Minesweeper from './components/Minsweeper';
//import Minesweepers from './components/Minsweepers';

export default {
  name: 'App',
  data: () => {
    return {
      row: [],
      col: [],
      mined: false,
      state: [],
      started: false,
    };
  },
  methods: {
    gameStart: function() {
      this.started = true;
//      this.generateGame(10, 20);
    },
    generateGame: function(rows=20, cols=10) {
      this.rows = rows;
      this.cols = cols;

    }
  },
}
</script>

<style>
body {
  font-family: Helvetica, sans-serif;
  background: #333;
  color: #fff;
}

#app button {
  display: block;
  margin: 50px auto;
}

table.minesweeper {
  margin: auto;
  border: 1px solid #999;
  border-collapse: collapse;
  background-color: #ddd;
}

table.minesweeper td {
  width: 24px;
  height: 24px;
  background-size: cover;
}

td.unopened {
  background: url('./assets/unopened.svg');
  cursor: pointer;
}

td.opened {
  background: url('./assets/opened.svg');
}

td.flagged {
  background: url('./assets/flag.svg');
  cursor: pointer;
}

td.mine {
  background: url('./assets/mine.png');
}

td.mine-neighbour-1 {
  background: url('./assets/1.svg');
}

td.mine-neighbour-2 {
  background: url('./assets/2.svg');
}

td.mine-neighbour-3 {
  background: url('./assets/3.svg');
}

td.mine-neighbour-4 {
  background: url('./assets/4.svg');
}

td.mine-neighbour-5 {
  background: url('./assets/5.svg');
}

td.mine-neighbour-6 {
  background: url('./assets/6.svg');
}

td.mine-neighbour-7 {
  background: url('./assets/7.svg');
}

td.mine-neighbour-8 {
  background: url('./assets/8.svg');
}
</style>
