<template>
  <q-page class="flex column justify-start">
    <div class="q-pa-md q-gutter-sm flex justify-center">
      <q-btn color="secondary" size="md" @click="navigate('/')">Novo pedido</q-btn>
      <q-btn color="secondary" size="md" @click="navigate('/')">Novo pagamento</q-btn>
      <q-btn color="primary" size="md" @click="navigate('/')">Relatórios</q-btn>
      <q-btn color="primary" size="md" @click="navigate('/')">Academy</q-btn>
    </div>
    <div v-ripple class="text-h2 text-blue-8 text-center q-ma-lg">
      Eventos de Hoje
    </div>
    <div class="row flex justify-center q-ma-md">
      <q-card flat bordered class="my-card" v-for="itemEvento in eventos" :key="itemEvento.descricaoEvento">
        <q-card-section>
          <div class="text-h5 text-center">{{ itemEvento.numeroDeEventos }}</div>
        </q-card-section>

        <q-card-section class="q-pt-none">
          <div class="text-center">{{ itemEvento.descricaoEvento }}</div>
        </q-card-section>
      </q-card>
    </div>
    <div class="flex justify-center q-ma-xl">
      <q-btn outline color="green-9" @click="navigate('/'), showNotification()"
        >Tarefas</q-btn
      >
      <q-btn outline color="green-9" @click="navigate('/'), showNotification()"
        >Produção</q-btn
      >
      <q-btn outline color="green-9" @click="navigate('/'), showNotification()"
        >Financeiro</q-btn
      >
      <q-btn outline color="green-9" @click="navigate('/'), showNotification()"
        >Estoque</q-btn
      >
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
      this.$router.push(router);
    },
  },
  setup() {
    const $q = useQuasar();

    function showNotification() {
      $q.notify("Você saiu do sistema");
    }

    return {
      showNotification,
      eventos: [
        {
          descricaoEvento: "Contas a pagar",
          numeroDeEventos: '5'
        },
        {
          descricaoEvento: "Boletos vencendo",
          numeroDeEventos: '2'
        },
        {
          descricaoEvento: "Cheques cadastrados",
          numeroDeEventos: '8'
        },
        {
          descricaoEvento: "Finalizados",
          numeroDeEventos: '12'
        },
        {
          descricaoEvento: "Pendentes",
          numeroDeEventos: '2'
        },
        {
          descricaoEvento: "Aniversariantes",
          numeroDeEventos: '0'
        }
      ],
    };
  },
});
</script>
