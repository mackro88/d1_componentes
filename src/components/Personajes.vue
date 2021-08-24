<template>
  <div id="contain">

    <ul v-for="character in characters" :key="character.id">
      <li><img :src="character.image" /> <span>{{ character.name }}</span></li>
                          
    </ul>
  </div>
</template>

<script>
    export default {
        data: () => ({
            characters: {},
        }),

        methods: {
            async getData() {
                try {
                    let response = await fetch("https://rickandmortyapi.com/api/character");
                    this.characters = await response.json();
                    this.characters = this.characters.results
                } catch (error) {
                    console.log(error);
                }
            },
        },

        created() {
            this.getData();
        },
    };
</script>

<style scoped>
#contain{ 
    margin: 0;
    padding: 0;
    background-image: url(https://rickandmortypod.com/wp-content/uploads/2018/11/cropped-RM_page-header_background1-3.png);
    background-repeat: no-repeat;
    background-size: cover;
}
ul {
    list-style: none;
}
li {
  color: rgb(24, 94, 33);
  font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
  font-size: large;
  display: flex;
  align-items: center;
}
img{
    border-radius: 50%;
    width: 100px;
    margin-right: 1rem;
}
</style>