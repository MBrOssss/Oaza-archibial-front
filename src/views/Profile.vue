<template>
  <div class="profile">
      <div class="grid-container">
          <div class="grid-item"><ProfileCard message-text=1 /></div>
          <div class="grid-item"><ProfileCard message-text=2 /></div>
          <div class="grid-item"><ProfileCard message-text=3 /></div>
      </div>
  </div>
</template>

<script>
import ProfileCard from '@/components/ProfileCard'

export default {
  name:"Profile",
  components: {ProfileCard}
}
</script>

<style lang='scss' scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,200;0,400;0,500;0,700;1,200;1,400;1,500&family=Varela+Round&display=swap');

.profile{
  height: 100vh;
  padding-top: 100px;
  color: #fefefe;
  font-family: Helvetica, sans-serif;

  .grid-container{
    display: grid;
    height: 100%;
    grid-template-rows: repeat(4,1fr);
      .grid-item{
        transition: .5s ease all;
        overflow: hidden;
      } 
  }



  @media(min-width: 770px){

    .grid-container{
    display: grid;
    height: 100%;
    grid-template-rows: repeat(5,1fr);
    grid-template-columns: repeat(4,1fr);

    .grid-item{
        // overflow: hidden;




        &:nth-child(2){
          grid-column-start: 1;
          grid-column-end: 3;
          grid-row-start: 3;
          grid-row-end: 5;
        }

        &:nth-child(1){
          grid-column-start: 1;
          grid-column-end: 3;
          grid-row-start: 1;
          grid-row-end: 3;
        }

        &:nth-child(3){
          grid-column-start: 3;
          grid-column-end: 6;
          grid-row-start: 1;
          grid-row-end: 5;
        }


    }
  }
  }
}
</style>