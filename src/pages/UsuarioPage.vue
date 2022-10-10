<template>
  <q-page padding>
    <div class="row q-mb-sm">
      <h4 class="q-my-xs col-9"> Usuários </h4>
      <div class="col-3 row justify-end">
        <q-btn @click="createUsuarioDialog = true" color="primary" class="q-ma-xs" icon="add">
          <q-tooltip>Adicionar</q-tooltip>
        </q-btn>
      </div>
    </div>
    <q-table
      :data="listUsuarios"
      :columns="usuarioTableColumns"
      row-key="id"
    >
      <template v-slot:body="props">
        <q-tr :props="props">
          <q-td key="id" :props="props">{{props.row.id}} </q-td>
          <q-td key="name" :props="props">{{props.row.name}} </q-td>
          <q-td key="ativo" :props="props">{{props.row.ativo.label}} </q-td>
          <q-td key="acao" :props="props">
            <div class="row items-center justify-center no wrap">
              <q-btn icon="create" @click="updateUsuarioAcao(props.row.id)" size="sm" round dense color="warning"
              class="q-mr-xs"></q-btn>
            </div>
          </q-td>
        </q-tr>
      </template>
    </q-table>
  </q-page>
</template>

<script>
export default {
  name: 'UsuarioPage',
  data () {
    return {
      createUsuarioDialog: false,
      listUsuarios: [
        {
          id: 1,
          name: 'John Doe',
          ativo: {
            value: true,
            label: 'Ativo'
          }
        }
      ],
      usuarioTableColumns: [
        {
          name: 'id',
          label: 'Id',
          field: 'id',
          align: 'center'
        },
        {
          name: 'name',
          label: 'Name',
          field: 'name',
          align: 'left'
        },
        {
          name: 'ativo',
          label: 'Ativo',
          field: 'ativo',
          align: 'left'
        },
        {
          name: 'acao',
          label: 'Ações',
          field: 'acao',
          align: 'center'
        }
      ]
    }
  },
  methods: {
    updateUsuario (id) {

    },
    createUsuario () {

    }
  }
}
</script>
