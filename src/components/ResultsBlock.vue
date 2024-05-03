<template>
  <p>Reaction Time : {{ score }} ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
props:["score"],
data(){
return{
  rank : null
}
},
mounted(){
  if(this.score<250){
    this.rank = "Ninja Fingers"
  }else if(this.score<450){
    this.rank = "Rapid Reflexes"
  }else{
    this.rank = "Snail pace..."
  }
}
}
</script>

<style>
.rank{
  width: 400px;
  height: 50px;
    border-radius: 20px;
    background: #0faf87;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}
</style>