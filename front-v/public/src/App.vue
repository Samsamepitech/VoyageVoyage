<template>
  <router-view/>
</template>

<style>
@import '@/assets/base.css';
body{
  background: no-repeat center center fixed url("assets/background-travel.png");
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  width: 100%;
  height: 100%;
  overflow: scroll;
}
#app{

  width:100%;
  height:100%;
  font-size: 20px;
}

a,
.green {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
}
@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

@media (min-width: 1024px) {
  body {
    display: flex;
    place-items: center;
  }
}
</style>
