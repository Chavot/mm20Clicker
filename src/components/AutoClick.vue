<template>
  
<button class="upgrades" @click.prevent="playSound('http://codeskulptor-demos.commondatastorage.googleapis.com/descent/gotitem.mp3')" @click="autoClick" :disabled="clicks<cost">{{name}} ({{cps}} cps) 
   {{cost}} coins</button>



</template>

<script>

export default {
    props: ['cost', 'cps', 'name', 'clicks', 'index'],
    methods: {
        autoClick(){
            this.$emit('clicked', this.index);


        },
            playSound (sound) {
      if(sound) {
        var audio = new Audio(sound);
        audio.play();
      }
    }
}
}
</script>





<style>
.upgrades{
    border-radius: 8px;
    padding: 15px;
    font-size: 22px;
    margin-top: 50px;
    margin-bottom: 0px;
    margin-left:15px;
    color:rgb(120, 0, 240);
    background-color: rgb(238, 158, 104);
    border: 4px dotted #6e0044; 
    cursor: pointer;
}
.upgrades:disabled{
background: #dddddd;
opacity:50%;
cursor: not-allowed; 
    }

</style>