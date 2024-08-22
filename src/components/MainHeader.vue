<script>
export default {
    data() {
        return {
            navLinkNames: [
              {
                 pageName: "Home",
                 name: "home"
              },
              {
                 pageName: "Projects",
                 name: "projects"
              },
              {
                 pageName: "About",
                 name: "about"
              }
            ]
        }
    }
}
</script>

<template>
  <div class="d-flex justify-content-evenly align-items-center">

    <h1>Header</h1>
    <ul class="d-flex justify-content-center align-items-center m-0 list-unstyled">
      <li class="ms-2" v-for="link in navLinkNames"><router-link class="text-decoration-none text-black" :to="{ name: link.name }">{{ link.pageName }}</router-link></li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>

</style>