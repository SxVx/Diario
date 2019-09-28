<template>
  <div id="app" class="morpheus-den-gradient">
    
    <template>
      <mdb-navbar expand="large" dark color="indigo" class="z-depth-2">
          <mdb-navbar-brand href="#">
              Diario
          </mdb-navbar-brand>
          <mdb-navbar-toggler right>
          <mdb-navbar-nav right>
              <mdb-nav-item href="#" active>Home</mdb-nav-item>
              <mdb-nav-item href="#">Link</mdb-nav-item>
              <mdb-nav-item class="disabled" href="#">Disabled</mdb-nav-item>
          </mdb-navbar-nav>
          </mdb-navbar-toggler>          
      </mdb-navbar>
    </template>
    <router-view/>
  </div>
</template>

<script>
import { mdbDropdown, mdbDropdownToggle, mdbDropdownMenu, mdbCol,mdbDropdownItem, mdbContainer, mdbNavbar, mdbNavbarBrand, mdbNavbarToggler, mdbNavbarNav, mdbNavItem } from 'mdbvue';
export default {
  name: 'App',
  components: {
    mdbNavbar,
    mdbNavbarBrand,
    mdbNavbarToggler,
    mdbNavbarNav,
    mdbNavItem,
    mdbContainer,
    mdbDropdown,
    mdbDropdownToggle,
    mdbDropdownMenu,
    mdbDropdownItem,
    mdbCol
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;  
  min-height: 100vh;
}
</style>
