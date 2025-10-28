<template>
  <div>
    <h1 style="color: darkblue">SOY COMICS - PADRE</h1>
    <div>
        <form v-on:submit.prevent="createComic()">
            <label for="">Titulo</label>
            <input type="text" v-model="newComic.titulo">
            <label>Imagen</label>
            <input type="text" v-model="newComic.imagen">
            <label>Descripcion</label>
            <input type="text" v-model="newComic.descripcion">
            <lbael>Año</lbael>
            <input type="number" v-model="newComic.year">
            <button>Nuevo Comic</button>
        </form>
    </div>
    <h2 v-if="favorito != null">Su comic favorito es: {{favorito.titulo}}</h2>
    <div  id="comics" v-for="(comic,index) in comics" :key="comic">
        <ComicComponent :comic="comic" :index="index" 
        v-on:elegirFavorito="mostrarFavorito" v-on:deleteComic="deleteComic" />
    </div>
  </div>
</template>

<script>
import ComicComponent from "./ComicComponent.vue";

export default {
  name: "ComicsComponent",
  components: {
    ComicComponent,
  },
  data() {
    return {
      comics: [
        {
          titulo: "Spiderman",
          imagen:
            "https://3.bp.blogspot.com/-i70Zu_LAHwI/T290xxduu-I/AAAAAAAALq8/8bXDrdvW50o/s1600/spiderman1.jpg",
          descripcion: "Hombre araña",
          year: 1997,
        },
        {
          titulo: "Wolverine",
          imagen:
            "https://images-na.ssl-images-amazon.com/images/I/51c1Q1IdUBL._SX259_BO1,204,203,200_.jpg",
          descripcion: "Lobezno",
          year: 2003,
        },
        {
          titulo: "Avengers",
          imagen:
            "https://d26lpennugtm8s.cloudfront.net/stores/057/977/products/ma_avengers_01_01-891178138c020318f315132687055371-640-0.jpg",
          descripcion: "Los Vengadores",
          year: 1993,
        },
        {
          titulo: "Spawn",
          imagen:
            "https://i.pinimg.com/originals/e1/d8/ff/e1d8ff4aeab5e567798635008fe98ee1.png",
          descripcion: "Al Simmons",
          year: 2000,
        },
        {
          titulo: "Batman",
          imagen:
            "https://www.comicverso.com/wp-content/uploads/2020/06/The-Killing-Joke-657x1024.jpg",
          descripcion: "Murcielago",
          year: 2001,
        },{
          titulo: "Guardianes de la Galaxia",
          imagen:
            "https://cdn.normacomics.com/media/catalog/product/cache/1/thumbnail/9df78eab33525d08d6e5fb8d27136e95/g/u/guardianes_galaxia_guadianes_infinito.jpg",
          descripcion: "Yo soy Groot",
          year: 2006,
        }
      ],
      favorito: null,
      newComic: {
        titulo: "",
        imagen: "",
        descripcion: "",
        year: 0
      }
    };
  },
  methods: {
    mostrarFavorito(fav){
        this.favorito = fav
    },
    createComic(){
        this.comics.push(this.newComic)
    },
    deleteComic(ind){
        this.comics.splice(ind,1)
    }
  }
};
</script>