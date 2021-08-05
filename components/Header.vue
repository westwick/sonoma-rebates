<template>
  <div id="header">
    <div class="container mx-auto">
      <header>
        <div class="logo">
          <NuxtLink to="/"
            ><img
              src="~/assets/gridsavvy/Mendocino/images/logo.svg"
              class="ml-4 my-6 md:ml-0"
          /></NuxtLink>
        </div>
        <div class="nav-toggle text-xl md:hidden mr-4">
          <i class="fas fa-bars" v-if="!showNav" @click="toggleNav(true)"></i>
          <i class="fas fa-times" v-if="showNav" @click="toggleNav(false)"></i>
        </div>
        <div class="header-right hidden md:flex items-center">
          <div class="rebates-dropdown" @click="toggleDropdown()">
            Rebates <i class="fas fa-chevron-down"></i>
          </div>
          <div class="rebates-dropdown-links" v-if="showDropdown">
            <NuxtLink to="/rebates/heat-pump">Heat Pump</NuxtLink>
            <NuxtLink to="/rebates/heat-pump-water-heater"
              >Heat Pump Water Heater</NuxtLink
            >
            <NuxtLink to="/rebates/induction-cooktop"
              >Induction Cooktop</NuxtLink
            >
          </div>
          <NuxtLink to="/apply" class="button-cta text-purp"
            >Get Started</NuxtLink
          >
        </div>
      </header>
    </div>
    <nav v-if="showNav">
      <p
        class="nav-link-group text-right px-3 py-1 text-sm uppercase font-bold"
      >
        Rebates
      </p>
      <p class="text-right p-3">
        <NuxtLink to="/rebates/heat-pump">Heat Pump</NuxtLink>
      </p>
      <p class="text-right p-3">
        <NuxtLink to="/rebates/heat-pump-water-heater"
          >Heat Pump Water Heater</NuxtLink
        >
      </p>
      <p class="text-right p-3">
        <NuxtLink to="/rebates/induction-cooktop">Induction Cooktop</NuxtLink>
      </p>
      <p
        class="nav-link-group text-right px-3 py-1 text-sm uppercase font-bold"
      >
        Application
      </p>
      <p class="text-right p-3"><NuxtLink to="/apply">Apply Now</NuxtLink></p>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showDropdown: false,
      showNav: false,
    }
  },
  methods: {
    toggleDropdown() {
      this.showDropdown = !this.showDropdown
    },
    toggleNav(vis) {
      this.showNav = vis
    },
  },
  watch: {
    $route() {
      this.showDropdown = false
      this.showNav = false
    },
  },
}
</script>

<style>
header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.header-right {
  /* display: flex;
  align-items: center; */
  position: relative;
}
.rebates-dropdown {
  color: rgba(79, 82, 99, 0.8);
  font-size: 18px;
  font-weight: bold;
  margin-right: 48px;
  cursor: pointer;
}
.rebates-dropdown:hover {
  color: rgba(79, 82, 99, 1);
}

.rebates-dropdown i {
  color: rgba(223, 224, 84, 1);
  font-size: 20px;
}

.rebates-dropdown-links {
  position: absolute;
  left: 0;
  top: 64px;
  background: #fff;
  width: 400px;
  border-top: 3px solid rgba(79, 82, 99, 1);
  display: flex;
  flex-direction: column;
  padding: 24px;
}

.rebates-dropdown-links a {
  font-weight: bold;
  margin-bottom: 8px;
  font-size: 18px;
}

.rebates-dropdown-links a:last-child {
  margin-bottom: 0;
}
nav {
  border-top: 1px solid #e8e8e8;
  user-select: none;
}
.nav-toggle {
  cursor: pointer;
}
nav a {
  font-weight: bold;
  color: #00b9d4;
}
/* nav p {
  border-bottom: 1px solid #f2f4f6;
} */
</style>
