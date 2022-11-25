<template>
  <div class="card acid-text p-3 my-3">
  <img :src="CD.poster" class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title"> {{ CD.title }} </h5>
    <h6 class="card-text"> {{ CD.author }} </h6>
    <p class="card-text"> {{ CD.year }} </p>
    <!-- <a href="#" class="btn btn-primary">Go somewhere</a> -->
  </div>
</div>
</template>

<script>
export default {
  name: 'CardComp',
  props: {
    CD: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.card{
  width: 18%;
  height: 350px;

   img{
    max-width: 100%;
    aspect-ratio: 1/1;

   }
}

//*************** my Utility ***************** */

.acid-text{
    /* font-size: 2rem; */
    display: inline-block;
    cursor: pointer;
    text-decoration: none;
    background-color: #202531;
    color: yellowgreen;
    border: 0.125em solid yellowgreen;
    padding: 0.25em 1em;
    border-radius: 0.25em;

    text-shadow: 0 0 0.125em white,
    0 0 0.125 currentColor;

    box-shadow: inset 0 0 0.5em 0 yellowgreen,
    0 0 0.5em 0 yellowgreen;

    position: relative;

    transition: background-color 0.5s;
}


.acid-text::before{
    pointer-events: none;
    content: "";
    position: absolute;
    background-color: yellowgreen;
    top: 120%;
    left: 0;
    width: 100%;
    height: 100%;

    transform: perspective(1em) rotateX(40deg) scale(1, 0.35);
    filter: blur(2em);
    opacity: 0.7;
}

.acid-text::after{
    content: "";
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    box-shadow: 0 0 2em yellowgreen;
    opacity: 1;
    background-color: yellowgreen;
    z-index: -1;
    transition: 1s linear;
}

.acid-text:hover,
.acid-text:focus{
    background-color: yellowgreen;
    color: #202531;
    text-shadow: none;
}

.acid-text:hover::after{
    opacity: 1;
}


</style>
