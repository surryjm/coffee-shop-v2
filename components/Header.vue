<!-- HEADER COMPONENT -->

<template>

  <div class="Header">
    <div id="nav">
      <div class="row">
        <!-- JUMBOTRON AND NAV -->
        <header class="col-sm-12 col-12 jumbotron jumbotron-fluid background-image">
          <!-- REWROTE NAV WITH BOOTSTRAP VUE -->
          <b-navbar toggleable="lg" type="dark" class="navbar navbar-expand-lg d-flex flex-row justify-content-between align-items-start">
            <b-navbar-brand class="navbar-brand text-white text-uppercase d-flex flex-column align-items-center">
              <h1 class="display-1">Ten Ton</h1>
              <h1 class="display-3">Coffee</h1>
            </b-navbar-brand>
            <div align="right">
            <!-- NAV TOGGLES TO HAMBURGER MENU AT LG BREAKPOINT -->
              <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
              <b-collapse id="nav-collapse" is-nav>
                <b-navbar-nav class="text-uppercase text-right">
                  <b-nav-item class="text-white" to="/">Home</b-nav-item>
                  <b-nav-item class="text-white" to="/about">About</b-nav-item>
                  <b-nav-item class="text-white" to="/menu">Menu</b-nav-item>
                  <b-nav-item class="text-white" to="/contact">Contact</b-nav-item>
                </b-navbar-nav>
              </b-collapse>
            </div>
          </b-navbar>
        </header>
      </div>
    </div>
  </div>
  
</template>

<script>
export default {
  name: "Header"
}
</script>