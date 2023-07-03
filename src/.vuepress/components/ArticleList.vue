<template>
    <div>
      <h3> 記事一覧 </h3>
        <ul>
            <li v-for="item in articles">
                <router-link v-bind:to="getLink(item.index)">
                {{ item.title }}: {{ item.date }}
                </router-link>
            </li>
        </ul>
    </div>
</template>

<script>
  export default {
    data() {
      return {
        articles: [
            { 
              "title": "私にとってのイラストについて",
              "date": "2023-07-03",
              "index": 2
            },
            {
                "title": "自作HPを作った",
                "date": "2023-07-02",
                "index": 1
            }
        ]
      }
    },
    methods: {
      getLink(value) {
        return '/articles/' + value + '.html'

      }
    }
  }
</script>