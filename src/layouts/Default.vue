<head>
    <!-- Global site tag (gtag.js) - Google Analytics -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-5T3V4LSBMC"></script>
    <script>
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());
    
      gtag('config', 'G-5T3V4LSBMC');
    </script>
    
    <!-- Hotjar Tracking Code for https://logandtwig.com -->
    <script>
        (function(h,o,t,j,a,r){
            h.hj=h.hj||function(){(h.hj.q=h.hj.q||[]).push(arguments)};
            h._hjSettings={hjid:1644347,hjsv:6};
            a=o.getElementsByTagName('head')[0];
            r=o.createElement('script');r.async=1;
            r.src=t+h._hjSettings.hjid+j+h._hjSettings.hjsv;
            a.appendChild(r);
        })(window,document,'https://static.hotjar.com/c/hotjar-','.js?sv=');
    </script>
</head>

<template>
  <div>
    <div class="layout">
      <header class="header">
        <g-link to="/">
          <g-image alt="LNT Logo" class="logo" src="~/assets/lnt-logo.png" width="200" />
        </g-link>
        <nav class="nav">
          <g-link class="nav-link" to="/">HOME</g-link>
          <g-link class="nav-link" to="/team">TEAM</g-link>
          <g-link class="nav-link" to="/join">JOIN US</g-link>
          <g-link class="nav-link" to="/about/">ABOUT</g-link>
          <Hamburger
            class="hamburger"
            v-bind:class="{ open: showDropDown }"
            v-on:click.native="toggleDropdown"
          />
        </nav>
        <transition name="slide-fade">
          <div class="dropdown" v-if="showDropDown">
            <g-link to="/">HOME</g-link>
            <g-link to="/team">TEAM</g-link>
            <g-link to="/join">JOIN US</g-link>
            <g-link to="/about/">ABOUT</g-link>
          </div>
        </transition>
      </header>
      <slot />
    </div>
    <footer>
      <div class="footer-content">
        <p>Log & Twig AB 2020</p>
        <a href="mailto:contact@logandtwig.se">contact@logandtwig.se</a>
        <a href="https://www.linkedin.com/company/logandtwig">@linkedin</a>
      </div>
    </footer>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
import Hamburger from "../components/Hamburger.vue";

export default {
  components: {
    Hamburger
  },
  data() {
    return {
      showDropDown: false
    };
  },
  methods: {
    toggleDropdown: function(event) {
      this.showDropDown = !this.showDropDown;
    }
  }
};
</script>

<style lang="scss">
@font-face {
  font-family: Inter-Regular;
  src: url("../assets/inter/Inter-Regular.woff");
  font-weight: normal;
}

@font-face {
  font-family: Inter-Light;
  src: url("../assets/inter/Inter-Light-BETA.woff");
  font-weight: normal;
}

@font-face {
  font-family: Inter-Medium;
  src: url("../assets/inter/Inter-Medium.woff");
  font-weight: normal;
}

.logo {
  width: 70px;
}

@media only screen and (max-width: 600px) {
  footer {
    p {
      display: none;
    }
  }

  .nav-link {
    display: none;
  }

  h1 {
    font-size: 40px;
  }

  .logo {
    width: 60px;
  }
}

@media only screen and (min-width: 600px) {
  .hamburger {
    display: none;
  }

  h1 {
    font-size: 50px;
  }

  .layout {
    width: 100%;
  }
}

h1 {
  font-family: Inter-Medium;
  font-weight: 400;
  font-style: normal;
  letter-spacing: 0em;
  line-height: 1.09em;
  text-transform: none;
  color: #000;
  margin-bottom: 0px;
}

h4 {
  font-family: Inter-Light;
}
p {
  font-family: Inter-Light;
  color: #9e9e9e;
  font-size: 24px;
}

.dropdown {
  position: absolute;
  top: 100px;
  background: white;
  z-index: 9998;
  box-sizing: border-box;
  text-align: center;
  overflow-x: hidden;
  overflow-y: hidden;
  right: 0;
  bottom: 0;
  left: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;

  a {
    font-size: 36px;
  }
}

a {
  font-family: Inter-Regular;
  font-weight: 400;
  font-style: normal;
  letter-spacing: 0em;
  line-height: 1.6em;
  text-transform: none;
  text-decoration: none;
  color: #333;
}

.slide-fade-enter-active {
  transition: all 0.1s ease;
}
.slide-fade-leave-active {
  transition: all 0.2s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter,
.slide-fade-leave-to {
  opacity: 0;
}

body {
  font-family: Inter-Regular;
  background: #fbfbf754;
  margin: 0;
  padding: 0;
  line-height: 1.5;
}

footer {
  background: #108971;
  display: flex;
  justify-content: space-around;

  .footer-content {
    min-height: 100px;
    width: 100%;
    display: flex;
    justify-content: space-around;
    align-items: center;
    max-width: 1200px;
    margin: auto 0;
  }

  a,
  p {
    font-family: Inter-Medium;
    color: white;
    font-size: 16px;
    min-width: 50px;
    text-decoration: none;
  }
}

#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  margin: 0 auto;
}
.layout {
  max-width: 1200px;
  padding-left: 20px;
  padding-right: 20px;
  margin: 0 auto;
  flex: 1;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 100px;
}

.nav-link {
  margin-left: 20px;
  font-size: 18px;
  font-family: Inter-Medium;
}
</style>
