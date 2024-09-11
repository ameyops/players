<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  name: String,
  matches: String,
  role: String,
  runs: String,
  _50s: String,
  _100s: String,
  highest_score: String,
  best_bowling_figures: String,
  team_id: String,
  team_name: String,
  image: String
});

console.log("qwerty");
console.log(props.matches);
</script>

<template>
    
        <div class="player-card">
            <img :src="image" alt="Player Image" class="player-image"/>
            <h1>{{ name }}</h1>
            <p><strong>Matches:</strong> {{ matches }}</p>
            <p><strong>Role:</strong> {{ role }}</p>
            <p><strong>Runs:</strong> {{ runs }}</p>
            <p><strong>50s:</strong> {{ _50s }}</p>
            <p><strong>100s:</strong> {{ _100s }}</p>
            <p><strong>Highest Score:</strong> {{ highest_score }}</p>
            <p><strong>Best Bowling Figures:</strong> {{ best_bowling_figures }}</p>
            <p><strong>Team ID:</strong> {{ team_id }}</p>
            <p><strong>Team Name:</strong> {{ team_name }}</p>
        </div>
    
  </template>

  <style >
  .card{   
    justify-content: center;  
    flex-direction: row;  
}
.player-card {
    border: 1px white;
    border-radius: 8px;
    padding: 16px;
    max-width: 300px;
    margin: 16px auto;
    background-color: skyblue;
    text-align: center;
    
}

.player-image {
  width: 100%;
  height: auto;
  border-radius: 8px;
}
</style>
