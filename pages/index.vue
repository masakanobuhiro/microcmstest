<template>
<ul>
<li v-for="content in contents" :key="content.id">
<nuxt-link :to="`/${content.id}`">
{{ content.title }}
</nuxt-link>
</li>
</ul>
</template>
<script>
import axios from 'axios'
export default {
async asyncData() {
const { data } = await axios.get(
// your-service-id部分は⾃分のサービスidに置き換えてください
'https://nobu3nobu3.microcms.io/api/v1/blog',
{
// your-api-key部分は⾃分のapi-keyに置き換えてください
headers: { 'X-API-KEY': '55b81a7d-21e9-4452-b2b7-0798bf819a2c' }
}
)
return data
}
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
