<template>
  
    <section>
        
        <form class="d-flex flex-wrap pt-3">

            <div class="col-sm-12 col-md-6 d-flex justify-content-around">
                <input @keyup.enter="startFilterGenere" class="col-sm-8 col-md-8" type="text" placeholder="Cerca per genere!" v-model.trim="searchGenere">
                <button @click.prevent="startFilterGenere" class="col-sm-3 btn btn-info col-md-3">Genere</button>
            </div>

            <div class="col-sm-12 col-md-6 d-flex justify-content-around">
                <input @keyup.enter="startFilterAlbum" class="col-sm-8 col-md-8" type="text" placeholder="Cerca per album!" v-model.trim="searchAlbum">
                <button @click.prevent="startFilterAlbum" class="col-sm-3 btn btn-warning col-md-3">Album</button>
            </div>

        </form>

    </section>

</template>

<script>
export default {

    data(){
        return{
            searchGenere: "",
            searchAlbum: ""
        }
    },

    methods:{
        startFilterGenere(){
            this.$emit("searchGen",this.searchGenere)
        },

        startFilterAlbum(){
            this.$emit("searchAlb",this.searchAlbum)
        }
    }
}
</script>

<style lang="scss" scoped>

input{
    height: 38px;
}

button{
    margin-right: 10px;
    margin-left: 10px;
}


</style>