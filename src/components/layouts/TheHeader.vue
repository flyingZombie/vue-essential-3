<template>
  <div class="navbar navbar-default topnav">
    <div class="container">
      <div class="navbar-header">

        <button type="button" class="navbar-toggle" @click="toggleNav">
          <span class="sr-only">Toggle navigation</span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
        </button>

        <a href="/" class="navbar-brand">
          <span class="title">{{ logo.title }}</span>
          <img :src="logo.src" :alt="logo.title">
        </a>
      </div>

      <div id="top-navbar-collapse" :class="['collapse', 'navbar-collapse', { in: showCollapsedNav }]">
        <ul class="nav navbar-nav">
          <li v-for="(item, index) in navList" :class="{ active: index === activeNavIndex }">
            <a href="#" @click="changeNavIndex(index)">{{ item }}</a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'TheHeader',
    data() {
      return {
        logo: {
          src: '/static/images/1_Primary_logo_on_transparent_295x65.png',
          title: 'LesterJs'
        },
        navList: ['Forum', 'HeadLines', 'Q&A', 'Tutorials'],
        activeNavIndex: 0,
        showCollapsedNav: false
      }
    },
    beforeCreate() {
        //this.uploadsUrl = 'https://*/uploads/'

    },
    methods: {
      changeNavIndex(index) {
        this.activeNavIndex = index
      },
      toggleNav() {
      this.showCollapsedNav = !this.showCollapsedNav
    }
    }
    }
</script>

<style scoped>

.title { display: none;}
.navbar-default .navbar-nav > .active > a { background: rgba(0,0,0,.09);}

</style>
