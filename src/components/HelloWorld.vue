<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      app
      clipped
    >
      <v-list dense>
        <v-list-item link>
          <v-list-item-action>
            <v-icon medium>home</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Informations générales</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link>
          <v-list-item-action>
           <v-icon medium>info</v-icon>
          </v-list-item-action>
          <v-list-item-content v-on:click="isHidden = !isHidden">
            <v-list-item-title>Informations détaillé</v-list-item-title>
            
          </v-list-item-content>
          
        </v-list-item>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-antenna</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Conditions générales</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      clipped-left
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title>Informations coronavirus</v-toolbar-title>
    </v-app-bar>
<v-alert type="error">
        Alerte, nous allons probablement tous mourrir.
      </v-alert>
    <v-content>
      
      <v-container

      
        class=""
        fluid
      >

      <div id="app" >
  <v-app id="inspire" >
    
    <v-card
      class=""
      max-width="344"
      outlined
    >
      <v-list-item three-line>
        <v-list-item-content>
          <div class="overline mb-2" >Actuellement infecté</div>
          <v-list-item-title class="headline mb-1">{{infected}}</v-list-item-title>
          <v-list-item-subtitle>Dernière mise à jour le : 28/02/2020 15:06</v-list-item-subtitle>

         

          
        </v-list-item-content>
         
  

      </v-list-item>

      
    </v-card>
<div>
  <div v-if="!isHidden">
    <br><br>
  <v-card
      class=""
      max-width="674"
      height="300"
      outlined
    >

      <v-list-item three-line>
        <v-list-item-content>
          <div class="overline mb-2" >En détail :</div>
          <v-list-item-title class="headline mb-1"><center>Parmis les {{infected }} infectés</center></v-list-item-title>
          <hr style="background-color:grey; height: 0.5px; border-color:white;">
          <br>
          <v-list-item-title class="headline mb-2"><u>Il y a :</u> {{dead}} morts</v-list-item-title><br>
          <v-list-item-title class="headline mb-2">{{recover}} qui ont survécu</v-list-item-title>
          <br><br>
          <v-list-item-subtitle>Dernière mise à jour le : 28/02/2020 15:06</v-list-item-subtitle>

         

          
        </v-list-item-content>
         
  

      </v-list-item>

      
    </v-card>
  
  </div>
</div>



  </v-app>
</div>

        <v-row
          align="left"
          justify="left"
        >
          <v-col class="shrink">
            <v-tooltip left>
            </v-tooltip>
            <v-tooltip left>
            
            </v-tooltip>
          </v-col>
        </v-row>
      </v-container>
    </v-content>

    <v-footer app>
      <span>DUPLOUY Antoine &copy; 2019</span>
    </v-footer>
  </v-app>
  
</template>


<script>

  export default {


    props: {
      source: String,
    },
    data: () => ({
      infected: '83 774',
      dead: '2 867',
      recover: '36 654',
      drawer: null,
      isHidden: true,
    }),
    created () {
      this.$vuetify.theme.dark = true
    },
    
  }
</script>