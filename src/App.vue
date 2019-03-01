<template>
  <v-app>
    <v-toolbar app color="primary" v-if="Show">

      <!-- <v-toolbar-side-icon></v-toolbar-side-icon> -->
      <v-toolbar-title>标题</v-toolbar-title>
      <v-toolbar-items class="hidden-sm-and-down">
          <v-btn flat v-on="on">栏目一</v-btn>
          <v-btn flat>栏目二</v-btn>
          <v-btn flat>栏目三</v-btn>
      </v-toolbar-items>
      <v-menu :nudge-width="100">
        <template v-slot:activator="{ on }">
          <v-toolbar-title flat v-on="on">
            <span>All</span>
            <v-icon dark>arrow_drop_down</v-icon>
          </v-toolbar-title>
        </template>
        <v-list>
          <v-list-tile v-for="item in items" :key="item" @click="">
            <v-list-tile-title v-text="item"></v-list-tile-title>
          </v-list-tile>
        </v-list>
      </v-menu>
      <!-- <v-tabs v-model="active" color="cyan" dark slider-color="yellow">
        <v-tab v-for="n in 3" :key="n" ripple>Item {{ n }}</v-tab>
        <v-tab-item v-for="n in 3" :key="n">
          <v-card flat>
            <v-card-text>{{ text }}</v-card-text>
          </v-card>
        </v-tab-item>
      </v-tabs> -->
    </v-toolbar>
        
    <v-content>
      <Header v-if="isShow"/>
    </v-content>
  </v-app>
</template>

<script>
import Header from './components/Header'

export default {
  name: 'App',
  components: {
    Header
  },
  data () {
    return {
      isShow:false,
      Show:true,
      items: [
        'All', 'Family', 'Friends', 'Coworkers'
      ]
    }
  },
  mounted : function(){
		//可用于设置自适应屏幕，根据获得的可视宽度（兼容性）判断是否显示
    let w = document.documentElement.offsetWidth || document.body.offsetWidth;
    if(w<640){
      //适应手机
      this.Show = false;
      this.isShow = true;
    }else if(w>640&&w<980){
      //适应平板
    }else if(w>980){
      //适应电脑
      this.Show = true;
      this.isShow = false;
    }
  }
}
</script>
