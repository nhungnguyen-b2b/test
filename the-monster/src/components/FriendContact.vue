<template>
  <div class="container" :style="cssVars">
    <div class="health-box">
      <h3 class="title">Monster Health</h3>
      <div class="health-bar">
        <div class="monster-health"></div>
      </div>
    </div>
    <div class="health-box">
      <h3 class="title">Monster Health</h3>
      <div class="health-bar">
        <div class="your-health"></div>
      </div>
    </div>
    <div class="button-box">
      <button @click="attack">ATTACK</button>
      <button>SPECIAL ATTACK</button>
      <button>HEAL</button>
      <button>SURRENDER</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "FriendContact",
  data() {
    return {
      monsterHealth: 100,
      yourHeath: 100,
    };
  },
  methods: {
    attack() {
      this.monsterHealth = this.monsterHealth - 10;
    },
  },
  computed: {
    cssVars() {
      return {
        /* variables you want to pass to css */
        "--monster-health": `${this.monsterHealth}%`,
        "--your-health": `${this.yourHealth}%`,
        "--color": "#123432",
      };
    },
  },
  watch: {
    checkHealth: function() {
      console.log(this.monsterHealth);
      if (this.monsterHealth == 0) {
        alert("you win!");
      }
    },
  },
};
</script>
<style scoped lang="scss">
.health-box {
  height: 200px;
  width: 450px;
  box-shadow: 5px 5px 5px lightgray;
  border-radius: 10px;
  padding: 30px;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;

  .title {
    font-size: 20px;
  }

  .health-bar {
    height: 50px;
    width: 400px;
    border: 2px solid #313131;
  }
  .monster-health {
    height: 50px;
    width: var(--monster-health);
    transition: all 0.5s;
    background-color: var(--color);
  }
  .your-health {
    height: 50px;
    width: var(--your-health);
    transition: all 0.5s;
    background-color: #088d56;
  }
}
.button-box {
  width: 300px;
  height: 150px;
  margin-top: 30px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 40px;

  button {
    border: none;
    border-radius: 10px;
    background-color: rgb(212, 59, 41);
    color: white;
    cursor: pointer;
    transition: all 0.5s;
    &:hover {
      background-color: salmon;
    }
  }
}
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: auto;
}
</style>
