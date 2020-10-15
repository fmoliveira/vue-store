<template>
  <div class="nav-bar">
    <div class="logo">Vue Store</div>
    <input id="nav-checkbox" type="checkbox" class="nav-checkbox" />
    <label for="nav-checkbox" class="nav-button">
      <span class="nav-icon" />
    </label>
    <div class="menu">
      <nav class="nav-menu">
        <a href="#">Home</a>
        <a href="#">Top 10</a>
        <a href="#">Contact</a>
      </nav>
      <div class="cart">
        0 items in cart
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style scoped>
.nav-bar {
  padding: 24px;
  background-image: linear-gradient(160deg, #0fd4a5, #3fd975 100%);
}

.logo {
  float: left;
  font-weight: bold;
  text-transform: uppercase;
}

.menu {
  clear: both;
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.2s ease-out;
}

.menu a {
  margin: 8px 0;
  padding: 12px;
  display: block;
  border: 2px solid;
  color: #146631;
  text-decoration: none;
}

.menu a:hover {
  background-image: linear-gradient(160deg, #22aa51, #28cc62 100%);
  color: white;
}

.nav-checkbox {
  display: none;
}

/* hamburger menu */

.nav-button {
  float: right;
  padding: 8px 0;
}

.nav-icon {
  background: #333;
  display: block;
  height: 2px;
  position: relative;
  width: 16px;
}

.nav-icon:before,
.nav-icon:after {
  content: "";
  display: block;
  background: #333;
  height: 100%;
  width: 100%;
  position: absolute;
  transition: all 0.2s ease-out;
}

.nav-icon:before {
  top: 5px;
}

.nav-icon:after {
  top: -5px;
}

.nav-checkbox:checked ~ .menu {
  max-height: 240px;
}

.nav-checkbox:checked ~ .nav-button .nav-icon {
  background: transparent;
}

.nav-checkbox:checked ~ .nav-button .nav-icon:before,
.nav-checkbox:checked ~ .nav-button .nav-icon:after {
  top: 0;
}

.nav-checkbox:checked ~ .nav-button .nav-icon:before {
  transform: rotate(-45deg);
}

.nav-checkbox:checked ~ .nav-button .nav-icon:after {
  transform: rotate(45deg);
}

/* end of hamburger-menu */

@media (min-width: 48em) {
  .nav-bar {
    padding: 12px;
    display: flex;
    align-items: center;
  }

  .menu {
    flex: 1;
    clear: none;
    max-height: none;
    display: flex;
    align-items: center;
  }

  .nav-menu {
    flex: 1;
    display: flex;
    justify-content: center;
  }

  .nav-icon {
    display: none;
  }

  .menu a {
    margin: 0 8px;
    float: left;
  }
}
</style>
