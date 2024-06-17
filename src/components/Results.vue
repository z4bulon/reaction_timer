<template>
  <h2>Your reaction time is {{score}} ms</h2>
  <p v-if="rank === 'Rapid Reflexes'" class="rank rapid">{{rank}}</p>
  <p v-else-if="rank === 'Snail pace'" class="rank snail">{{rank}}</p>
  <p v-else class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props:['score'],
  data(){
    return{
      rank:null,
    }
  },
  mounted() {
    if(this.score < 300){
      this.rank = 'Rapid Reflexes'
    }
    else if(this.score > 400){
      this.rank = 'Snail pace'
    }
    else{
      this.rank = 'Average'
    }
  }
}
</script>

<style>
  .rank{
    font-size:1.4em;
    color: #2c3e50;
    font-weight: bold;
  }
  .snail{
    color:crimson;
  }
  .rapid{
    color: #0faf87;
  }
</style>