<template>
    <div id="app">
        <div data-icon="ei-spinner-2" data-size="l" ></div>
        <hello></hello>
        <reviews-requested></reviews-requested>
        <your-repositories></your-repositories>
    </div>
</template>

<script>
    import Hello from './components/Hello';
    import ReviewsRequested from './components/ReviewsRequested';
    import YourRepositories from './components/YourRepositories';
    export default {
        components: {
            Hello,
            ReviewsRequested,
            YourRepositories
        }
    };
</script>

<style>
  html {
    height: 100%;
  }
  body {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
  }
  #app {
    margin-top: -100px;
    max-width: 600px;
    font-family: Helvetica, sans-serif;
    text-align: center;
  }
  .logo {
    width: 100px;
    height: 100px
  }
</style>
