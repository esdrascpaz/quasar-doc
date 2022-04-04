<template>
  <q-page class="flex column justify-center">
    <div class="">
      <!-- <div class="q-gutter-sm justify-end full-width row q-pr-xl"></div> -->

      <div v-ripple class="text-h1 text-center q-ma-xl">Sistema LABFácil</div>
    </div>
    <div class="full-width">
      <div class="row q-gutter-sm justify-center items-center">
        <div class="">
          <q-btn
            label="Login"
            @click="navigate('/inicio'), showNotification()"
          />
        </div>
      </div>
    </div>
  </q-page>
</template>

<script>
import { useQuasar } from "quasar";
import { defineComponent } from "vue";

export default defineComponent({
  name: "MainLayout",

  components: {},
  methods: {
    navigate(router = "") {

      
      // Por padrão é vazio
      this.$router.push(router); // $router é um methodo do vue
    },
  },

  setup() {
    const $q = useQuasar();

    function showNotification() {
      $q.notify("Login efetuado com sucesso");
    }

    return {
      showNotification,
    };
  },
});
</script>
