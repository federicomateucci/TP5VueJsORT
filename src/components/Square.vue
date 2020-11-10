<template>
    <div :style="square" @click="squareClick()"></div>
</template>

<script>

  export default  {
    name: 'src-components-square',
    props: [
      'index',
      'square','fsquare', 
      'mensajes','fmensajes',
      'pickedColor',
      'setAllColorsTo'
    ],
    mounted () {

    },
    data () {
      return {

      }
    },
    methods: {
      squareClick(){
        var clickedColor = this.square.backgroundColor;
        if (clickedColor === this.pickedColor) {
          this.fmensajes.messageDisplay("You Picked Right!");
          this.setAllColorsTo(this.pickedColor);
          this.fmensajes.restartButton("Play Again!");
          //this.mensajes.restartButton = "Play Again!";  // --> NO!
          this.fmensajes.headerColor(this.pickedColor);
        } else {
          this.fsquare.backgroundColor(this.index,"#232323");
          //this.square.backgroundColor = "#232323"; // --> NO!
          this.fmensajes.messageDisplay("Try Again!");
        }
      }
    },
    computed: {
    }
}


</script>

<style scoped lang="css">
</style>
