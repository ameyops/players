<script setup>
import players from '../data/players.js';
import CardComponent from '../components/CardComponent.vue';

console.log(players);
</script>

<template>
    <div>

        <div class="card">
            <CardComponent 
            v-for="(player, index) in players" 
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