<template>
  <div>
    <div class="container-top">
      <div>
        <div class="col-4 right-offset-2 container-top__left">
          <div class="col-3">
            <h2>dc comics</h2>
            <ul>
              <a :href="elm.url" v-for="(elm, i) in footerMenu.dcComics" :key="i"><li>{{elm.name}}</li></a>
            </ul>
            <h2>shop</h2>
            <ul>
              <a :href="elm.url" v-for="(elm, i) in footerMenu.shop" :key="i"><li>{{elm.name}}</li></a>
            </ul>
          </div>
          <div class="col-3">
            <h2>dc</h2>
            <ul>
              <a :href="elm.url" v-for="(elm, i) in footerMenu.dc" :key="i"><li>{{elm.name}}</li></a>
            </ul>
          </div>
          <div class="col-3">
            <h2>sites</h2>
            <ul>
              <a :href="elm.url" v-for="(elm, i) in footerMenu.sites" :key="i"><li>{{elm.name}}</li></a>
            </ul>
          </div>
        </div>
        <div class="col-4 logo">
        </div>
      </div>
    </div>
    <div class="container-bottom">
      <div>
        <div class="container-bottom__left">
          <a href="#"><span>sign-up now!</span></a>
        </div>
        <div class="container-bottom__right">
          <span>follow us</span>
          <ul>
            <li v-for="(elm, i) in social" :key="i"><a :href="elm.url"><img :src="elm.img" :alt="elm.name + 'logo'" target="_blank"></a></li>
            <!-- TARGET BLANK NON FUNZIONA -->
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
name: 'FooterComp',
data(){
  return{
    footerMenu : {
      dcComics : [
        {
          name : "characters",
          url : "#"
        },
        {
          name : "comics",
          url : "#"
        },
        {
          name : "movies",
          url : "#"
        },
        {
          name : "tv",
          url : "#"
        },
        {
          name : "games",
          url : "#"
        },
        {
          name : "videos",
          url : "#"
        },
        {
          name : "news",
          url : "#"
        }
      ],
      shop : [
        {
          name : "shop DC",
          url : "#"
        },
        {
          name : "shop DC collectibles",
          url : "#"
        },
      ],
      dc : [
        {
          name : "terms of use",
          url : "#"
        },
        {
          name : "privacy policy (New)",
          url : "#"
        },
        {
          name : "ad choices",
          url : "#"
        },
        {
          name : "advertising",
          url : "#"
        },
        {
          name : "jobs",
          url : "#"
        },
        {
          name : "subscription",
          url : "#"
        },
        {
          name : "talent workshops",
          url : "#"
        },
        {
          name : "CPSC certificates",
          url : "#"
        },
        {
          name : "ratings",
          url : "#"
        },
        {
          name : "shop help",
          url : "#"
        },
        {
          name : "contacts us",
          url : "#"
        },
      ],
      sites : [
        {
          name : "DC",
          url : "#"
        },
        {
          name : "MAD magazine",
          url : "#"
        },
        {
          name : "DC kids",
          url : "#"
        },
        {
          name : "DC universe",
          url : "#"
        },
        {
          name : "DC power visa",
          url : "#"
        },
      ]
    },
    social : [
      {
        name : "facebook",
        img : require("../assets/img/footer-facebook.png"),
        url : "https://www.facebook.com/dc/"
      },
      {
        name : "twitter",
        img : require("../assets/img/footer-twitter.png"),
        url : "https://twitter.com/dccomics"
      },
      {
        name : "youtube",
        img : require("../assets/img/footer-youtube.png"),
        url : "https://www.youtube.com/channel/UCiifkYAs_bq1pt_zbNAzYGg"
      },
      {
        name : "pinterest",
        img : require("../assets/img/footer-pinterest.png"),
        url : "https://www.pinterest.it/dccomics/"
      },
      {
        name : "periscope",
        img : require("../assets/img/footer-periscope.png"),
        url : "#"
      }
    ]
  }
}
}
</script>

<style scoped lang='scss'>
// 10 colonne
@for $i from 1 through 10{
  .col-#{$i}{max-width: 100%/10 * $i; flex-basis: 100%/10 * $i;}
}

// right offset 10 colonne
@for $i from 1 through 10{
  .right-offset-#{$i}{margin-right: 100%/10 * $i;}
}
.container-top{
  background-image: url(../assets/img/footer-bg.jpg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  &__left{
    display: flex;
    padding: 2em 0.5em 3em;
    h2{
      color: #fff;
      text-transform: uppercase;
      font-size: 1rem;
      font-weight: 700;
      margin: 0.5em 0;
    }
    a{
      color: #797c7c;
      text-transform: capitalize;
      font-size: 0.8rem;
      margin: 0.3em 0;
      display: block;
    }
  }
}

.container-top > div{
  width: 70%; 
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
}

.col-4.logo{
  background-image: url(../assets/img/dc-logo-bg.png);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

.container-bottom{
  background-color: #303030;
  &__left{
    span{
      text-transform: uppercase;
      color: #fff;
      border: 1px solid #0282f9;
      padding: 0.5em;
      font-size: 0.8rem;
      font-weight: 700;

      &:hover{
        background-color: #0282f9;
      }
    }
  }
  &__right{
    display: flex;
    align-items: center;
    margin: 1em 0;
    ul{
      display: flex;
      flex-wrap: nowrap;
    }
    span{
      text-transform: uppercase;
      color: #0282f9;
      margin-right: 1em;
      font-weight: 700;
    }
    img{
      width: 60%;
      height: auto;
      margin: 0 0.5em;
    }
  }
}

.container-bottom > div{
  width: 70%; 
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>