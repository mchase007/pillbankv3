<template>
    <Header></Header>
    <EasyNav></EasyNav>
    <section class="search-container2">

    <Search></Search>
    </section>
    
    <section class="container">
        <section class="drug-details">
        <p class="hd2">{{drugInfor[id].drug}}</p>
        <p class="hd1">How it works</p>

            <div v-if="drugInfor">
                <p>{{drugInfor[id].levelOne}}</p>
                <span class="button" v-if="!levelTwo" @click="displayMore">Read more</span>
            </div>
            <div v-if="levelTwo">
                <p>{{drugInfor[id].levelTwo}}</p>
                <a class="button" @click="displayMore" v-if="!levelTwo">Read more</a>
                <a class="button" @click="displayMore" v-if="levelTwo">Less Details</a>
            </div>
            <div>
                <p @click="displayQuestion" class="question">Lorem ipsum dolor sit amet?</p>
                <div v-if="question">
                    <p>{{drugInfor[id].QuestionOne}}</p>
                </div>
            </div>
        </section>

    </section>
    
<!-- <div v-else>
    <p>Loading Drug Data</p>
</div> -->
</template>

<script>
import Header from '@/components/Header.vue'
import EasyNav from '@/components/EasyNav.vue'
import Hero from '@/components/Hero.vue'
import Search from '@/components/Search.vue'
import json from '@/assets/data/db.json';

export default {
    props: ['id','drugName'],
    components: { Header,EasyNav,Hero,Search },
    // inheritAttrs: false,
    data() {
        return {
            drugInfor: json.data,
            levelTwo: false,
            question: false,
        }
    },
    
    mounted() {
    },
  methods: {
      displayMore() {
          this.levelTwo = !this.levelTwo
          console.log('more' + this.levelTwo)
      },
      displayQuestion() {
          this.question = !this.question
          console.log(this.question)
      }
  },
}
</script>

<style lang="scss" scoped>
    
    $pillWhite: hsl(181, 77%, 97%);
    $pillGreen: hsl(181, 77%, 25%);
     
    .hero_container {
        background: $pillGreen;
    }
    .search-container2 {
        background: $pillGreen;
        width: 100%;
        margin: 0 auto;
    }
    .container {
        padding-bottom: 20px;
    }
    .drug-details {
        width: 95%;
        max-width: 750px;
        margin: 0 auto;

        .question {
            margin-top: 40px;
            padding: 5px 0;
            border-top: 2.8px solid hsl(181, 77%, 25%);
            border-bottom: 2.8px solid hsl(181, 77%, 25%);
            cursor: pointer;
        }

    }

    .button {
        border: 1.5px solid hsl(181, 77%, 25%);
        border-radius: 2.5px;
        color: hsl(181, 77%, 25%);
        padding: 7px;
        // margin-top: 100px;
        cursor: pointer;    
    }

    .button:hover {
        color: $pillWhite;
        background-color: $pillGreen;
    }

    .hd1 {
        color: hsl(181, 77%, 25%);
        font-size: 1rem;
        line-height: 24px;
        font-weight: 700;
        margin-bottom: -10px;
    }

    .hd2 {
        color: hsl(181, 77%, 25%);
        font-size: 2rem;
        line-height: 24px;
        font-weight: 400;
    }
    
    p {
        color: hsl(181, 77%, 25%);
        font-size: 1.14rem;
        line-height: 24px;
        padding-bottom: 10px;
    }

    .easy-nav {
        background-color: hsl(181, 77%, 25%);

        &::v-deep a {
            color: hsl(181, 77%, 97%);
            
        }

        &.open {
        padding-top: 70px;
        }
    }

    .hero {

        height: 150px;
        
        &::v-deep p {
            display: none;
        }

        &.open {
            padding-top: 20px;
        }
    }

    @media only screen and (min-width: 770px) {
    .drug-details div {
        p{
            font-size: 1.2rem;
            padding-bottom: 10px;
        }
    }
}

</style>