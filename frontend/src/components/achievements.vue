<template>
  <div class="achievements-container">
    <h2 class="achievements-h2">Za naše fungovanie sa nám podarilo</h2>
    <div class="achievements-flexbox">
      <div v-for="achievement in achievements"
           class="achievement-item">
        <h3>{{ achievement.attributes.number }}</h3>
        <p>{{ achievement.attributes.name }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

const LOCALHOST_URL = "http://localhost:1337/";
export default {
  name: "achievements",
  data() {
    return {
      achievements: []
    }
  },
  mounted() {
    axios.get(LOCALHOST_URL + "api/achievements")
        .then(res => {
          this.achievements = res.data.data;
          console.log(res.data.data);
        })
        .catch(err => console.log(err));
  }
}
</script>

<style scoped lang="scss">
.achievements-container {
  background: #e3b75e;
  padding: 3rem;
}

.achievements-flexbox {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 20px;
  margin-top: 5rem;
}

.achievement-item {
  padding: 1rem;
  width: 250px;

  h3 {
    font-size: 5rem;
  }

  p {
    font-size: 2rem;
  }
}

.achievements-h2 {
  text-align: center;
  font-size: 3rem;
  margin: 2rem 1rem;
}
</style>