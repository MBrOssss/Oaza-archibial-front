<template>
  <header :class="{ 'scrolled-nav': scrolledNav }">
    <nav>
      <div class="branding">
        <img src="@/assets/logo.png" alt="" />
      </div>

      <ul v-show="!mobile" class="navigation">
        <li>
          <router-link class="link" :to="{ name: 'Home' }">
            <i class="fa-solid fa-house-chimney"></i>
          </router-link>
        </li>
        <li>
          <router-link class="link" :to="{ name: 'Profile' }"
            >Profil</router-link
          >
        </li>
        <li>
          <router-link class="link" :to="{ name: 'Enroll' }"
            >Zapisy</router-link
          >
        </li>
        <li>
          <router-link class="link" :to="{ name: 'AdminPanel' }"
            >Panel administratora</router-link
          >
        </li>
        <!-- <li><router-link class="link" :to="{name: ''}">Zaloguj</router-link></li>   -->
      </ul>

      <div class="icon">
        <i
          @click="toggleMobileNav"
          v-show="mobile"
          class="fa-solid fa-bars"
          :class="{ 'icon-active': mobileNav }"
        ></i>
      </div>

      <transition name="mobile-nav">
        <ul v-show="mobileNav" class="dropdown-nav">
          <li>
            <router-link class="link" :to="{ name: 'Home' }"
              >Strona główna</router-link
            >
          </li>
          <li>
            <router-link class="link" :to="{ name: 'Profile' }"
              >Profil</router-link
            >
          </li>
          <li>
            <router-link class="link" :to="{ name: 'Enroll' }"
              >Zapisy</router-link
            >
          </li>
          <li>
            <router-link class="link" :to="{ name: 'AdminPanel' }"
              >Panel administratora</router-link
            >
          </li>
          <!-- <li><router-link class="link" :to="{name: ''}">Zaloguj</router-link></li> -->
        </ul>
      </transition>
    </nav>
  </header>
</template>

<script>
export default {
  name: "Navigation",
  data() {
    return {
      scrolledNav: null,
      mobile: true,
      mobileNav: null,
      windowWidth: null,
    };
  },
  created() {
    window.addEventListener("resize", this.checkScreen);
    this.checkScreen();
  },
  mounted() {
    window.addEventListener("scroll", this.updateScroll);
  },
  methods: {
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav;
    },

    updateScroll() {
      const scrollPosition = window.scrollY;
      if (scrollPosition > 50) {
        this.scrolledNav = true;
        return;
      }
      this.scrolledNav = false;
    },

    checkScreen() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth <= 1090) {
        this.mobile = true;
        return;
      }
      this.mobile = false;
      this.mobileNav = false;
      return;
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,200;0,400;0,500;0,700;1,200;1,400;1,500&display=swap");

* {
  padding: 0;
  margin: 0;
}

header {
  font-family: "Poppins", Helvetica, sans-serif;
  background-color: #fff;
  z-index: 99;
  width: 100%;
  position: fixed;
  transition: 0.5 ease all;
  border-bottom: 3px solid #eee;

  nav {
    display: flex;
    flex-direction: row;
    padding: 12px 0;
    transition: 0.5s ease all;
    width: 90%;
    margin: 0 auto;
    color: #333;
    @media (min-width: 1140px) {
      max-width: 1140px;
    }
  }

  ul,
  .link {
    font-weight: 500;
    list-style: none;
    text-decoration: none;
    color: #333;
    transition: 0.5s ease all;
    i {
      font-size: 18px;

      &:hover {
        font-weight: 700;
      }
    }
  }

  li {
    text-transform: uppercase;
    padding: 16px;
    margin-left: 16px;
  }

  .link {
    font-size: 16px;
    transition: 0.5s ease all;
    padding-bottom: 6px;
    border-bottom: 3px solid transparent;

    &:hover {
      font-weight: 700;
      border-color: #98d1c9;
      transition: 0.3s ease all;
    }
  }

  .branding {
    display: flex;
    align-items: center;

    img {
      width: 200px;
      height: 50px;
      transition: 0.5s ease all;
      @media (min-width: 550px) {
      width: 300px;
      height: 60px;
      transition: 0.5s ease all;
      }
    }
  }

  .navigation {
    display: flex;
    align-items: center;
    flex: 1;
    justify-content: flex-end;
  }

  .icon {
    display: flex;
    align-items: center;
    position: absolute;
    top: 0;
    right: 24px;
    height: 100%;

    i {
      cursor: pointer;
      font-size: 24px;
      transition: 0.8s ease all;
    }
  }

  .icon-active {
    transform: rotate(90deg);
  }

  .dropdown-nav {
    display: flex;
    flex-direction: column;
    position: fixed;
    width: 250px;
    max-width: 250px;
    height: 100%;
    background-color: #fff;
    top: 0;
    left: 0;
    border-right: 3px solid #eee;

    li {
      margin-left: 0;
      border-bottom: #e9e9e9 2px solid;
      .link {
        color: #333;
      }
    }
  }

  .mobile-nav-enter-active,
  .mobile-nav-leave-active {
    transition: 1s ease all;
  }

  .mobile-nav-enter-from,
  .mobile-nav-leave-to {
    transform: translateX(-250px);
  }

  .mobile-nav-enter-to {
    transform: translateX(0);
  }
}

.scrolled-nav {
  nav {
    padding: 8px 0;

    .branding {
      img {
        width: 150px;
        height: 30px;
      }
    }
  }
}
</style>
