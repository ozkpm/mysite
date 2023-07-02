<template>
    <div>
      <h3> 記事一覧 </h3>
        <ul>
            <li v-for="(item, index) in articles">
                <router-link v-bind:to="getLink(index)">
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
                "title": "自作HPを作った",
                "date": "2023-07-02"
            }
        ]
      }
    },
    methods: {
      getLink(value) {
        value = value + 1
        return '/articles/' + value + '.html'

      }
    }
  }
</script>