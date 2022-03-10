<template>
  <nav>
      <div class="container">
          <div class="items">
            <div class="left"><h1>eSpace</h1></div>
            <div class="right">
                <div class="input">
                    <img :src="Search" alt="" class="search">
                    <input type="text" placeholder="Search">
                </div>
                
            </div>

          </div>
      </div>
  </nav>
</template>

<script>
import Search from '../assets/magnifier.png'
export default {
    setup() {
    

    // expose to template and other options API hooks
    return {
      Search,
    }
  }
}
</script>

<style scoped>
    nav {
        border-bottom: 2px solid black;
        display:flex;
        justify-content: center;
    }
    .container {
        max-width: 1440px;
        width:90%;
    }
    .container .items {
        display:flex;
        align-items: center;
        justify-content: space-between;
    }
    input {
        outline: 0;
        border: 0;
        font-size:0.9em;
    }
    .input {
        padding:0.5rem 1rem;
        border-radius: 20px;
        border: 2px solid;
        background-color:rgb(255, 255, 255);
        display:flex;
        align-items: center;
    }
    .right img {
        margin-right:10px;
        width:20px;
        height:20px;
    }

</style>