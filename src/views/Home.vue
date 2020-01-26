<template>
  <div class="home">{{ works }}</div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import gql from "graphql-tag";

export default {
  name: "home",
  data() {
    return {
      hello: []
    };
  },
  components: {
    HelloWorld
  },
  apollo: {
    works: {
      query: gql`
        query($userId: Int!){
          works(userId: $userId) {
            name
          }
        }
      `,
      variables: {
        userId: 1,
      },
    }
  }
};
</script>
