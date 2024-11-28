<template>
  <div class="chess-grandmasters">
    <h1>Chess Grandmasters</h1>
    <div v-if="grandmasters.length === 0" class="loading">
      Loading...
    </div>
    <div v-else>
      <ul>
        <li v-for="(grandmaster, index) in grandmasters" :key="index">
          <GrandmasterCard :grandmaster="grandmaster" />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import GrandmasterCard from './GrandmasterCard.vue';

export default {
  name: 'ChessGrandmasters',
  components: {
    GrandmasterCard
  },
  data() {
    return {
      grandmasters: []
    };
  },
  created() {
    fetch("http://localhost:3000/api")
      .then(response => response.json())
      .then(data => {
        this.grandmasters = data.grandmasters;
      })
      .catch(error => {
        console.error("Error fetching data:", error);
      });
  }
};
</script>

<style scoped>
.chess-grandmasters {
  font-family: 'Arial', sans-serif;
  margin: 40px auto;
  max-width: 1000px;
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0px 4px 12px rgba(0, 0, 0, 0.1);
}

h1 {
  text-align: center;
  color: #4a90e2;
  font-size: 2.5rem;
  margin-bottom: 30px;
}

.loading {
  text-align: center;
  font-size: 1.5rem;
  color: #ff6f61;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  margin-bottom: 25px;
  padding: 15px;
  background-color: #ffffff;
  border-radius: 10px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-in-out;
}

li:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.2);
}

li:nth-child(odd) {
  background-color: #e0f7fa; /* Light cyan for odd items */
}

li:nth-child(even) {
  background-color: #fff3e0; /* Light orange for even items */
}

@media (max-width: 768px) {
  h1 {
    font-size: 2rem;
  }
  .chess-grandmasters {
    padding: 10px;
  }
  li {
    padding: 10px;
  }
}
</style>
