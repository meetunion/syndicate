<template>
  <div class="container">
    <Header
      :title="title"
      :description="description"
      :coverImageURL="coverImageURL"
    />
    <qrcode
      :value="ethAddress"
      :options="{ width: 200 }"
      v-if="ethAddress"
    ></qrcode>
  </div>
</template>

<script>
import Api from '../services/ApiManager'
import Header from '@/components/Header'
import qrcode from '@chenfengyuan/vue-qrcode'

export default {
  name: 'Home',
  components: { Header, qrcode },
  data: () => {
    return {
      title: '',
      description: '',
      coverImageURL: '',
      ethAddress: ''
    }
  },
  created() {
    this.fetchData()
  },
  methods: {
    fetchData() {
      Api.get('union').then(response => {
        this.title = response.data.title
        this.description = response.data.description
        this.coverImageURL = response.data.cover_image_url
        this.ethAddress = response.data.eth_address
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
