<template>
  
    <section class="col-md-6 col-lg-4 col-xl-3">

        <div class="container text-center">

            <img :src="carta.poster" :alt="carta.title">
            <h5>{{carta.title}}</h5>
            <p>{{carta.author}}</p>
            <p class="anno">{{carta.year}}</p>
        </div>

    </section>

</template>

<script>
export default {
    name: 'MainCard',
    props:{
        carta: Object
    }
}
</script>

<style style lang="scss" scoped>

.container{
    background-color: #2E3A46;
    margin-top: 30px;
    h5{
    color: white;
    margin-top: 20px;
    min-height: 70px;
    }
    img{
        max-height: 150px;
        margin-top: 20px;
    }
    p{
        color:#6C767D;
        line-height: 5px;
    }
    p.anno{
        padding-bottom: 20px;
    }
}

</style>