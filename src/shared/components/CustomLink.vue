<template>
  <a
    target="blank"
    v-if="isExternalLink"
    :href="link.to"
    :class="isActive ? 'is-Active' : 'normal-link'"
  >
    {{ link.name }}
  </a>

  <router-link  v-else :to="route" v-slot="{ isActive }">
    <a :href="href" :class="isActive ? 'is-Active' : 'normal-link'">{{
      link.name
    }}</a>
  </router-link>
</template>

<script>
export default {
  props: {
    link: {
      type: Object,
      required: true,
    },
  },
  computed: {
    isExternalLink() {
      return this.link.to.startsWith("https");
    },
    route(){
        return this.link.id === undefined
        ?{name:this.link.to}
        :{name:this.link.to,params:{id:this.link.id}}
    }
  },
};
</script>

<style scoped>
.is-Active {
  color: #42b983;
}
.normal-link {
  color: #c6c5c5;
}
</style>