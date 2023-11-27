<script setup>
  import { ref, computed } from 'vue';

  import Tabs from '@/components/Tabs.vue';

  const tabs = [
    {name: 'Сентябрь'},
    {name: 'Октябрь'},
    {name: 'Ноябрь'},
    {name: 'Декабрь'}
  ]
  const selectedTab = ref('Сентябрь')

  const septemberElements = [
    {date: '10.09.2023', town: 'Волгоград', href: ''},
    {date: '15.09.2023', town: 'Москва', href: ''},
    {date: '20.09.2023', town: 'Питер', href: ''},
  ]

  const octoberElements = [
    {date: '10.10.2023', town: 'Новгород', href: ''},
    {date: '15.10.2023', town: 'Рязань', href: ''},
    {date: '20.10.2023', town: 'Ростов', href: ''},
  ]

  const novemberElements = [
    {date: '10.11.2023', town: 'Киров', href: ''},
    {date: '15.11.2023', town: 'Томбов', href: ''},
    {date: '20.11.2023', town: 'Калининград', href: ''},
  ]

  const decemberElements = [
    {date: '10.12.2023', town: 'Вологда', href: ''},
    {date: '15.12.2023', town: 'Астрахань', href: ''},
    {date: '20.12.2023', town: 'Новокузнецк', href: ''},
  ]

  var curentArr = septemberElements
  const changeTab = (tabName) => {
    selectedTab.value = tabName
    switch(tabName){
      case 'Сентябрь':
        curentArr = septemberElements
        break;
      case 'Октябрь':
        curentArr = octoberElements
        break;
      case 'Ноябрь':
        curentArr = novemberElements
        break;
      case 'Декабрь':
        curentArr = decemberElements
        break;
      default:
        curentArr = septemberElements
        break;
    }
      
}
</script>





<template>
  <div class="start">
    <nav class="navbar">
      <div class="container">
        <div class="navbar-wrap">
          <ul class="navbar-menu">
            <li><a href="#"></a>КОНЦЕРТЫ</li>
            <li><a href="#"></a>ОБ АРТИСТЕ</li>
            <li><a href="#"></a>МУЗЫКА</li>
            <li><a href="#"></a>ОБРАТНАЯ СВЯЗЬ</li>
            <li><a href="#"></a>ВОЙТИ</li>
          </ul>
        </div>
      </div>
    </nav>

    <div class="logo">
      SHAMAN
    </div>
    <img src="./assets/shaman1.png" class="shaman1">
  </div>

  <div id="app"></div>

  <Tabs
  :names="tabs"
  :selectedTab="selectedTab"
  @changeTab="changeTab">
    <div v-for="elem in curentArr">
      <div class="line"></div>
      <div class="column">
        <div>
          <div class="elem">
            {{elem.date}}
          </div>
          <div class="elem">
            {{elem.town}}
          </div>
        </div>
        <div class="elem dop">
          Подробнее
        </div>
      </div>
    </div>
  </Tabs>
</template>





<style>
  .navbar{
    width: 100%;
    height: 27px;
    
    margin-left: 582px;
    font-family: 'B612';
    font-size: 20px;
  }

  .navbar .container{
    height: inherit;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .navbar-menu
  {
    list-style-type: none;
    padding-left: 0;
    margin-bottom: 0;
  }

  .navbar-menu li
  {
    display: inline-block;
    padding-left: 35px;
  }

  .navbar-menu li a
  {
    display: inline-block;
  }

  .navbar-wrap
  {
    display: flex;
    flex-flow: row nowrap;
  }





  .logo {
    color: #FFFFFF;
    font-size: 128px;
    font-family: 'B612';
    margin-top: 350px;
    margin-left: 752px;
    position: absolute;
  }

  .start
  {
    background: rgb(247,244,164);
    background: radial-gradient(circle at 0% -100%, rgba(247,244,164,1) 0%, rgba(0,0,0,1) 60%);
    justify-content: center;
    width: 1366px;
  }

  .shaman1
  {
    width: 943px;
    height: 665px;
    position: relative;

  }



  .column {
  display: flex;
  justify-content: space-between;
  flex-direction: row;
}
.line {
  height: 1px;
  background-color: rgb(255, 255, 255);
}
.elem {
  display: inline-block;
  padding-left: 50px;
  padding-right: 200px;
  padding-top: 10px;
  padding-bottom: 30px;
  font-size: 30px;
}
.dop {
  color: #F7F4A4;
  text-align: right;
  padding-right: 30px;
  font-size: 20px;
}
</style>
