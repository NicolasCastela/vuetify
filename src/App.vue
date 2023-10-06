<template>
  <v-app theme="dark">
    <v-app-bar flat class="border-b" title="">
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-app-bar-tittle>Meu titulo</v-app-bar-tittle>
      <template #append>
        <v-btn icon class="mr-2">
         <v-badge :content="9" color="info"> 
          <v-icon icon="mdi-bell-outline"></v-icon>
        </v-badge>
        </v-btn>
       
        <v-avatar >
          <v-img cover src="https://meragor.com/files/styles//ava_800_800_wm/the_spongebob_movie_sponge_out_of_water_art.jpg"></v-img>
        </v-avatar>
      </template>
    </v-app-bar>
    <v-main>
      <v-container>
        <h1>Dashboard</h1>
         <v-row>
           <v-col cols="12"  sm="6" md="4" lg="3" > 
            <v-card> 
              <v-img class="align-end text-white"
              src="https://images.pexels.com/photos/15743235/pexels-photo-15743235/free-photo-of-acao-atividade-movimento-bicicleta.png?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" >
              <v-card-title>Top 10 Tittle</v-card-title>
              </v-img>
               <v-card-subtitle class="pt-3">Teste</v-card-subtitle>
              <v-card-text> 
                <div> Rio vermelho</div>
                <div>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Accusamus aspernatur eius doloribus eum dolores deserunt velit incidunt debitis assumenda provident? Sint, illum. Ipsum quo ut cumque repellendus quod fugiat aperiam.</div>
                </v-card-text>
                <v-card-actions>
                  <v-card-actions>
                  <v-btn variant="outlined" color="primary">Ver mais</v-btn>
                  <v-btn  prepend-icon="mdi-cart" variant="tonal" color="blue">Comprar</v-btn>
                  <v-btn icon="mdi-home" variant="tonal" color="blue"></v-btn>
                  
                </v-card-actions>
                </v-card-actions>
              </v-card> 
            </v-col>
         
            <v-col cols="12"  sm="6" md="4" lg="3" > 
            <v-card> 
              <v-img class="align-end text-white"
              src="https://images.pexels.com/photos/15743235/pexels-photo-15743235/free-photo-of-acao-atividade-movimento-bicicleta.png?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" >
              <v-card-title>Top 10 Tittle</v-card-title>
              </v-img>
               <v-card-subtitle class="pt-3">Teste</v-card-subtitle>
              <v-card-text> 
                <div> Rio vermelho</div>
                <div>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Accusamus aspernatur eius doloribus eum dolores deserunt velit incidunt debitis assumenda provident? Sint, illum. Ipsum quo ut cumque repellendus quod fugiat aperiam.</div>
                </v-card-text>
                <v-card-actions>
                  <v-card-actions>
                  <v-btn variant="outlined" color="primary">Ver mais</v-btn>
                  <v-btn  prepend-icon="mdi-cart" variant="tonal" color="blue">Comprar</v-btn>
                  <v-btn icon="mdi-home" variant="tonal" color="blue"></v-btn>
                  
                </v-card-actions>
                </v-card-actions>
              </v-card> 
            </v-col>
             <v-col cols="12"   sm="6" md="4" lg="3" > 
            <v-card> 
              <v-img class="align-end text-white"
              src="https://images.pexels.com/photos/15743235/pexels-photo-15743235/free-photo-of-acao-atividade-movimento-bicicleta.png?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" >
              <v-card-title>Top 10 Tittle</v-card-title>
              </v-img>
               <v-card-subtitle class="pt-3">Teste</v-card-subtitle>
              <v-card-text> 
                <div> Rio vermelho</div>
                <div>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Accusamus aspernatur eius doloribus eum dolores deserunt velit incidunt debitis assumenda provident? Sint, illum. Ipsum quo ut cumque repellendus quod fugiat aperiam.</div>
                </v-card-text>
                <v-card-actions>
                 <v-card-actions>
                  <v-btn variant="outlined" color="primary">Ver mais</v-btn>
                  <v-btn  prepend-icon="mdi-cart" variant="tonal" color="blue">Comprar</v-btn>
                  <v-btn icon="mdi-home" variant="tonal" color="blue"></v-btn>
                  
                </v-card-actions>
                </v-card-actions>
              </v-card> 
            </v-col>
             <v-col cols="12"   sm="6" md="4" lg="3"> 
            <v-card> 
              <v-img class="align-end text-white"
              src="https://images.pexels.com/photos/15743235/pexels-photo-15743235/free-photo-of-acao-atividade-movimento-bicicleta.png?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" >
              <v-card-title>Top 10 Tittle</v-card-title>
              </v-img>
               <v-card-subtitle class="pt-3">Teste</v-card-subtitle>
              <v-card-text> 
                <div> Rio vermelho</div>
                <div>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Accusamus aspernatur eius doloribus eum dolores deserunt velit incidunt debitis assumenda provident? Sint, illum. Ipsum quo ut cumque repellendus quod fugiat aperiam.</div>
                </v-card-text>
                <v-card-actions>
                 <v-card-actions>
                  <v-btn variant="outlined" color="primary">Ver mais</v-btn>
                  <v-btn  prepend-icon="mdi-cart" variant="tonal" color="blue">Comprar</v-btn>
                  <v-btn icon="mdi-home" variant="tonal" color="blue"></v-btn>
                  
                </v-card-actions>
                </v-card-actions>
              </v-card> 
            </v-col>
        
         
         </v-row>
      </v-container>

     
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",

  components: {
    HelloWorld,
  },

  data: () => ({
    //
  }),
};
</script>
