<template>
  <nav class="navbar">
    <div class="wrapper">
      <div class="logo">
        <router-link to="/">
          <img :src="logo" alt="Logo">
        </router-link>
      </div>
      <ul class="nav-links">
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/products">Mycard</router-link></li>
        <li><router-link to="/about">About</router-link></li>
      </ul>
    </div>
  </nav>
</template>

<script>
import logo from "@/assets/logo.png";

export default {
  name: "MyBer",
  data() {
    return {
      logo,
      isMenuActive: false, // ใช้เพื่อควบคุมการแสดงผลเมนูในมือถือ
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuActive = !this.isMenuActive; // เปลี่ยนสถานะการแสดงผลของเมนู
    }
  }
};
</script>


<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
}

.navbar {
  background: linear-gradient(45deg, #0077ff, #acfffb);
  color: #fff;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 0 20px;
  overflow: hidden;
  box-shadow: 0 4px 10px rgba(0, 89, 255, 0.2);
  z-index: 1000;
}

.wrapper {
  max-width: 1300px;
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: auto;
}

.logo img {
  width: 50px;
  height: auto;
  margin-top: 10px;
}

.nav-links {
  display: flex;
  gap: 20px;
}

.nav-links li {
  list-style: none;
}

.nav-links li a {
  color: #000000;
  text-decoration: none;
  font-size: 18px;
  font-weight: 500;
  padding: 8px 20px;
  border-radius: 20px;
  transition: background 0.3s ease, transform 0.2s ease;
}

.nav-links li a:hover {
  background: rgba(255, 255, 255, 0.3);
  transform: scale(1.1);
}

@media (max-width: 768px) {
  .wrapper {
    flex-direction: column;
    height: auto;
    background-color: #ffffff;
  }

  .nav-links {
    display: none; /* Hide the menu by default */
    flex-direction: column;
    gap: 10px;
    margin-top: 10px;
    background-color: #ffffff;
  }

  .nav-links.active {
    display: flex; /* Show the menu when it's active */
  }

  .nav-links li a {
    font-size: 16px;
  }

  .menu-toggle {
    display: block;
    font-size: 24px;
    cursor: pointer;
  }
}
</style>

