<template>
    <div class="grandmaster-card">
      <h2>{{ grandmaster.name }}</h2>
      <p><strong>Country:</strong> {{ grandmaster.country_of_origin }}</p>
      <p><strong>Titles:</strong> {{ grandmaster.titles_held.join(', ') }}</p>
      <p><strong>Peak Elo Rating:</strong> {{ grandmaster.peak_elo_rating }}</p>
      <p><strong>Games Played:</strong> {{ grandmaster.number_of_games_played }}</p>
      <p><strong>Total Wins:</strong> {{ grandmaster.total_wins }}</p>
      <p><strong>Active Years:</strong> {{ grandmaster.active_years.start_year }} - {{ grandmaster.active_years.end_year || 'Present' }}</p>
    </div>
  </template>
  
  <script>
  export default {
    name: "GrandmasterCard",
    props: {
      grandmaster: Object
    }
  };
  </script>
  
  <style scoped>
  .grandmaster-card {
    padding: 20px;
    background-color: #ffffff;
    border-radius: 8px;
    box-shadow: 0px 2px 8px rgba(0, 0, 0, 0.1);
  }
  
  .grandmaster-card h2 {
    color: #333;
    font-size: 1.5rem;
    margin-bottom: 10px;
  }
  
  .grandmaster-card p {
    color: #555;
    font-size: 1rem;
    margin: 5px 0;
  }
  
  .grandmaster-card strong {
    color: #333;
  }
  </style>
  