<template>
  <div class="game">
    <AddPlayer v-on:add-player="addPlayer" />
    <Board :players="players"/>
    <button v-on:click="assignRoles">Assign Roles</button>
  </div>
</template>

<script>
import Board from "./Board";
import AddPlayer from "./AddPlayer";

export default {
  name: 'Game',
  components:{
    Board,
    AddPlayer
  },
  data() {
    return {
      players: [
        {
          id: "1",
          name: "Taro",
          role: "人狼"
        },
        {
          id: "2",
          name: "Jiro",
          role: "市民"
        },
        {
          id: "3",
          name: "Saburo",
          role: "騎士"
        }
      ]
    }
  },
    methods: {
      addPlayer(newPlayer) {
        this.players = [...this.players, newPlayer]
      },
      assignRoles: function() {
        this.players.forEach(player =>
          player.role = getRandomRole()
        )
  },
    }
}

function getRandomRole() {
  var roles = [
    { value: "Citizen", text: "市民" },
    { value: "Warewolf", text: "人狼" },
    { value: "FortuneTeller", text: "占い師" },
  ]
  var index = Math.floor(Math.random() * roles.length)

  return roles[index].text;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
