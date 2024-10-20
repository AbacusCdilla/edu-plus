<template>
    <div id="app">
      <header>
        <h1>Lesson Booking App</h1>
      </header>
      <main>
        <LessonList />
        <ShoppingCart />
        <Checkout />
      </main>
    </div>
  </template>
  
  <script>
  import LessonList from './components/LessonList.vue';
  import ShoppingCart from './components/ShoppingCart.vue';
  import Checkout from './components/Checkout.vue';
  
  export default {
    components: {
      LessonList,
      ShoppingCart,
      Checkout
    }
  }
  </script>
  
  <style>
  /* Add any global styles here */
  </style>