<template>
  <v-app :theme="cor">
    <v-navigation-drawer v-model="isDrawerOpen">
      <v-list>
        <v-list-subheader>Menu</v-list-subheader>
        <v-list-item prepend-icon="mdi-home">Home</v-list-item>
        <v-list-item prepend-icon="mdi-account">Usuário</v-list-item>
        <v-list-group value="usClientes">
          <template #activator="{ props }">
            <v-list-item
              v-bind="props"
              prepend-icon="mdi-account-circle"
              title="Clientes"
            >
            </v-list-item>
          </template>
          <v-list-item prepend-icon="mdi-currency-usd">Faturamento</v-list-item>
          <v-list-item prepend-icon="mdi-chart-line">Relatório</v-list-item>
        </v-list-group>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar flat class="border-b" title="">
      <v-app-bar-nav-icon
        @click="isDrawerOpen = !isDrawerOpen"
      ></v-app-bar-nav-icon>
      <v-app-bar-tittle>Meu titulo</v-app-bar-tittle>
      <!-- NOTIFICAÇÃO -->
      <template #append>
        <!-- DARK MODE -->
        <v-btn @click="alterarCor" icon="mdi-brightness-4" class="mr-2">
        </v-btn>
        <v-menu>
          <template #activator="{ props }">
            <v-btn v-bind:="props" icon class="mr-2">
              <v-badge v-bind:="props" :content="9" color="info">
                <v-icon icon="mdi-bell-outline"> </v-icon>
              </v-badge>
            </v-btn>
          </template>
          <v-card min-width="300px" min-height="200px ">
            <v-list lines="false" density="compact">
              <!-- 1   -->
              <v-list-item flat class="border-b" prepend-icon="mdi-alert">
                <v-list-item-title>Você tem algo pendente</v-list-item-title>
                <v-list-item-subtitle
                  >Verifique quanto antes para evitar possiveis problemas
                </v-list-item-subtitle>
              </v-list-item>
              <!--  2 -->
              <v-list-item flat class="border-b" prepend-icon="mdi-bomb">
                <v-list-item-title>Promoção explosiva</v-list-item-title>
                <v-list-item-subtitle
                  >Não perca as melhores ofertas</v-list-item-subtitle
                >
              </v-list-item>
            </v-list>
          </v-card>
        </v-menu>

        <v-menu>
          <template #activator="{ props }">
            <v-avatar v-bind:="props">
              <v-img
                cover
                src="https://meragor.com/files/styles//ava_800_800_wm/the_spongebob_movie_sponge_out_of_water_art.jpg"
              ></v-img>
            </v-avatar>
          </template>
          <v-card min-width="200px">
            <v-list lines="false" density="compact" nav>
              <!-- 1   -->
              <v-list-item prepend-icon="mdi-account-outline">
                <v-list-item-title>Meu perfil</v-list-item-title>
              </v-list-item>
              <!--  2 -->
              <v-list-item prepend-icon="mdi-heart-outline">
                <v-list-item-title>Favoritos</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-card>
        </v-menu>
      </template>
    </v-app-bar>

    <v-main>
      <v-container>
        <h1>Dashboard</h1>

        <v-card flat class="border mb-10">
          <div class="d-flex justify-space-between">
            <v-card-title>Últimos Usuários</v-card-title>
            <v-card-title>
              <v-btn @click="isDialogOpen = true" variant="tonal" size="small">Adicionar usuário</v-btn
              >
              <v-dialog v-model="isDialogOpen" width="600px">
                
                <v-card>
                  <v-card-title>Adicionar Usúario</v-card-title>
                 <v-card-text>
                  <v-row>
                    <v-col>
                      <v-text-field label="Nome" variant="outlined"> </v-text-field>
                    </v-col>
                    <v-col>
                      <v-text-field 
                      label="Email"
                       variant="outlined"
                       :rules="emailRules"> </v-text-field>
                    </v-col>
                  </v-row>
                  <v-select label="Cargo" variant="outlined"
                    :items="['Admin', 'Gerente', 'Convidado']">
                  </v-select>
                 </v-card-text>
                 <v-card-actions>
                  <v-spacer>
                  </v-spacer>
                  <v-btn variant="text" @click="isDialogOpen = false">Cancelar</v-btn>
                  <v-btn variant="tonal" color="success">Enviar</v-btn>
                 </v-card-actions>
                </v-card>
              </v-dialog>
            </v-card-title>


          </div>
          <v-table>
            <thead>
              <tr>
                <th>Nome</th>
                <th>Email</th>
                <th>Cargo</th>
                <th>Ações</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>Fulano</td>
                <td>Fulano@gmail.com</td>
                <td>Administrador</td>
                <td><v-btn variant="tonal" color="primary">Editar</v-btn></td>
              </tr>
              <tr>
                <td>Fulano</td>
                <td>Fulano@gmail.com</td>
                <td>Gerente</td>
                <td><v-btn variant="tonal" color="primary">Editar</v-btn></td>
              </tr>
              <tr>
                <td>Fulano</td>
                <td>Fulano@gmail.com</td>
                <td>Convidado</td>
                <td><v-btn variant="tonal" color="primary">Editar</v-btn></td>
              </tr>
            </tbody>
          </v-table>
        </v-card>

        <v-row>
          <v-col cols="12" sm="6" md="4" lg="3">
            <v-card>
              <v-img
                class="align-end text-white"
                src="https://images.pexels.com/photos/15743235/pexels-photo-15743235/free-photo-of-acao-atividade-movimento-bicicleta.png?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
              >
                <v-card-title>Top 10 Tittle</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-3">Teste</v-card-subtitle>
              <v-card-text>
                <div>Rio vermelho</div>
                <div>
                  Lorem, ipsum dolor sit amet consectetur adipisicing elit.
                  Accusamus aspernatur eius doloribus eum dolores deserunt velit
                  incidunt debitis assumenda provident? Sint, illum. Ipsum quo
                  ut cumque repellendus quod fugiat aperiam.
                </div>
              </v-card-text>
              <v-card-actions>
                <v-card-actions>
                  <v-btn variant="outlined" color="primary">Ver mais</v-btn>
                  <v-btn prepend-icon="mdi-cart" variant="tonal" color="blue"
                    >Comprar</v-btn
                  >
                  <v-btn icon="mdi-home" variant="tonal" color="blue"></v-btn>
                </v-card-actions>
              </v-card-actions>
            </v-card>
          </v-col>

          <v-col cols="12" sm="6" md="4" lg="3">
            <v-card>
              <v-img
                class="align-end text-white"
                src="https://images.pexels.com/photos/15743235/pexels-photo-15743235/free-photo-of-acao-atividade-movimento-bicicleta.png?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
              >
                <v-card-title>Top 10 Tittle</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-3">Teste</v-card-subtitle>
              <v-card-text>
                <div>Rio vermelho</div>
                <div>
                  Lorem, ipsum dolor sit amet consectetur adipisicing elit.
                  Accusamus aspernatur eius doloribus eum dolores deserunt velit
                  incidunt debitis assumenda provident? Sint, illum. Ipsum quo
                  ut cumque repellendus quod fugiat aperiam.
                </div>
              </v-card-text>
              <v-card-actions>
                <v-card-actions>
                  <v-btn variant="outlined" color="primary">Ver mais</v-btn>
                  <v-btn prepend-icon="mdi-cart" variant="tonal" color="blue"
                    >Comprar</v-btn
                  >
                  <v-btn icon="mdi-home" variant="tonal" color="blue"></v-btn>
                </v-card-actions>
              </v-card-actions>
            </v-card>
          </v-col>
          <v-col cols="12" sm="6" md="4" lg="3">
            <v-card>
              <v-img
                class="align-end text-white"
                src="https://images.pexels.com/photos/15743235/pexels-photo-15743235/free-photo-of-acao-atividade-movimento-bicicleta.png?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
              >
                <v-card-title>Top 10 Tittle</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-3">Teste</v-card-subtitle>
              <v-card-text>
                <div>Rio vermelho</div>
                <div>
                  Lorem, ipsum dolor sit amet consectetur adipisicing elit.
                  Accusamus aspernatur eius doloribus eum dolores deserunt velit
                  incidunt debitis assumenda provident? Sint, illum. Ipsum quo
                  ut cumque repellendus quod fugiat aperiam.
                </div>
              </v-card-text>
              <v-card-actions>
                <v-card-actions>
                  <v-btn variant="outlined" color="primary">Ver mais</v-btn>
                  <v-btn prepend-icon="mdi-cart" variant="tonal" color="blue"
                    >Comprar</v-btn
                  >
                  <v-btn icon="mdi-home" variant="tonal" color="blue"></v-btn>
                </v-card-actions>
              </v-card-actions>
            </v-card>
          </v-col>
          <v-col cols="12" sm="6" md="4" lg="3">
            <v-card>
              <v-img
                class="align-end text-white"
                src="https://images.pexels.com/photos/15743235/pexels-photo-15743235/free-photo-of-acao-atividade-movimento-bicicleta.png?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
              >
                <v-card-title>Top 10 Tittle</v-card-title>
              </v-img>
              <v-card-subtitle class="pt-3">Teste</v-card-subtitle>
              <v-card-text>
                <div>Rio vermelho</div>
                <div>
                  Lorem, ipsum dolor sit amet consectetur adipisicing elit.
                  Accusamus aspernatur eius doloribus eum dolores deserunt velit
                  incidunt debitis assumenda provident? Sint, illum. Ipsum quo
                  ut cumque repellendus quod fugiat aperiam.
                </div>
              </v-card-text>
              <v-card-actions>
                <v-card-actions>
                  <v-btn variant="outlined" color="primary">Ver mais</v-btn>
                  <v-btn prepend-icon="mdi-cart" variant="tonal" color="blue"
                    >Comprar</v-btn
                  >
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
export default {
  data() {
    return {
      cor:'white',
    };
  },
  methods: {
    alterarCor() {
      if (this.cor == "white") {
        this.cor = "dark";
      } else {
        this.cor = "white";
      }
     
       


    },
  },
};
</script>


<script setup>
import { ref } from "vue";

const isDrawerOpen = ref(false);
const isDialogOpen = ref(false);
const emailRules = [
  value => {
    if(value) {
      return true;
    } 
      return 'O email é obrigatorio';
    }
];
</script>


