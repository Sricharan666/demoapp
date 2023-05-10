<template>
  <div>
    <ul>
      <li v-for="(menu, index) in menus" :key="index">
        <a :href="menu.link" target="_blank">{{ menu.name }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menus: [
        { name: 'Home', link: '/' },
        { name: 'About', link: '/about' },
        { name: 'Google', link: 'https://www.google.com/' },
      ],
    };
  },
};
</script>
<style scoped>
  ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
   background-image: linear-gradient(to right, rgb(225, 118, 250), rgb(65, 80, 250));
    overflow:hidden;
  }

  li {
    float: left;
  }

  li a {
    display: block;
    color: #333;
    text-align: center;
    padding: 22px 22px;
    text-decoration: none;
  }

  li a:hover {
    background-color: #ddd;
  }
</style>
