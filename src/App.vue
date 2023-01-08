<template>
  <div class="container">
    <MyHeader />
    <div class="main">
      <DeviceInfo />
    </div>
  </div>
</template>

<script setup>
  import MyHeader from "@/MyHeader";
  import DeviceInfo from "@/DeviceInfo";
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    height: 100vh;
    background: #ddd;
    display: flex;
    justify-content: center;
    font-family: "Arial", sans-serif;
    user-select: none;
  }

  .container {
    margin: 10px 20px;
  }
  
   .block__wrap {
     max-width: 1120px;
     margin: 0 auto;
     display: flex;
     justify-content: center;
     flex-direction: row;
     flex-wrap: wrap;
   }

  @media(min-width: 680px) {
    h1 {
      text-align: center;
    }

    .container {
      margin-top: 15%;
    }

    .main {
      display: flex;
      flex-grow: 1;
      justify-content: space-around;
      align-items: top;
      column-gap: clamp(10px, 1em, 80px);
    }
  }
</style>