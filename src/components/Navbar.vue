<template>
   <nav class="navbar navbar-default" id="navbar">
       <div class="navbar-header">
           <router-link class="navbar-brand" to="/">Vue demo</router-link>
       </div>
       <ul class="nav navbar-nav">
          <li v-for="route in routes">
              <router-link to="{
            path: route.fullPath,
            exact: route.showInNavbar.exact,
            activeClass: 'active'
          }">
                  <i class="fa-lg m-r-5" :class="route.icon | defaultIcon"></i>
              </router-link>
          </li>
       </ul>
       <ul class="nav navbar-nav navbar-right m-r-5">
          <li data-toggle="tooltip" title="Github">
              <router-link to="https://github.com/kenberkeley/vue-demo">
                  <i class="fa fa-github fa-lg"></i>
              </router-link>
          </li>
          <li data-toggle="tooltip" title="文档">
              <router-link to="docs">
                  <i class="fa fa-book fa-lg"></i>
              </router-link>
          </li>
           <li v-if="$root.userData" class="dropdown">
               <a href="javascript:;" class="dropdown-toggle" data-toggle="dropdown">
                   <i class="fa fa-user-secret fa-lg m-r-5"></i>
                   {{ $root.userData.username }}
                   <span class="caret"></span>
               </a>
               <ul class="dropdown-menu">
                   <li><router-link to="`/auth/logout`">
                       <i class="fa fa-sign-out fa-lg m-r-5"></i>
                       注销登录
                   </router-link></li>
               </ul>
           </li>
           <li v-else router-link-active>
               <router-link to="{ path: '/auth/login', activeClass: 'active' }">
                   <i class="fa fa-sign-in fa-lg m-r-5"></i>
                   登录
               </router-link>
           </li>
       </ul>
   </nav>
</template>

<script>
import routesMap from 'routes/map/'
</script>

