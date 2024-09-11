<script setup>
import { computed, ref } from 'vue';
import players from '../data/players.js';
import CardComponent from '../components/CardComponent.vue';


const selected = ref('role');


const sortedPlayers = computed(() => {
  return [...players].sort((a, b) => {
    if (selected.value === 'role') {
      return b.runs - a.runs;
    } else if (selected.value === 'matches') {
      return b.matches - a.matches;
    } else if (selected.value === 'highest_score') {
      return b.highest_score - a.highest_score;
    }
    return 0;
  });
});
</script>

<template>
    <div>
        <select v-model="selected">
            <option value="role">Runs</option>
            <option value="matches">Matches</option>
            <option value="highest_score">Highest Score</option>
          </select>

        <div class="card">
            <CardComponent 
            v-for="(player, index) in sortedPlayers" 
            :key="index" 
            :name="player.name" 
            :matches="player.matches" 
            :role="player.role" 
            :runs="player.runs" 
            :50s="player._50s" 
            :100s="player._100s" 
            :highest_score="player.highest_score" 
            :best_bowling_figures="player.best_bowling_figures" 
            :team_id="player.team_id" 
            :team_name="player.team_name" 
            :image="player.image" />
        </div>
    </div>
</template>

<style scoped>
.card {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>