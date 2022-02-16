<template>
  <div class="card">
      <!-- <p>{{ messageText }}</p> -->
      <!-- Profil -->
      <div v-if="messageText == 1">
          <div class="profle-img">
              <i class="fa-solid fa-user-large fa-2xl" ></i>
          </div>
          <div class="card-element">
                Imię i nazwisko
          </div>
          <div class="card-element">
              <p>Pesel: X</p>
              <hr/>
              <p>Adres: X</p>
              <hr/>
              <p>Wiek: X</p>
              <hr/>
              <button class="edit-btn">Edytuj</button>
          </div>
      </div>
      <!-- Dodatkowe informacje -->
      <div v-if="messageText == 2">2</div>
      <!-- Historia oaz -->
      <div v-if="messageText == 3">3</div>
  </div>
</template>

<script>
export default {
    name: "ProfileCard",  
    // props:['messageText']
    props: {
        messageText: String
    }
}
</script>

<style lang='scss'>
    .card{
        height: 100%;
        background: #333;
        color: white;
        margin: 10px;
        // border: #333 solid 1px;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
    }
</style>