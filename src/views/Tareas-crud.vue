<template>
  <v-container grid-list-sm>
    <NavBar />
    <v-layout row wrap mx-4>
      <v-flex md6 v-if="formAgregar">
        <v-card class="mb-3 pa-3">
          <v-form @submit.prevent="agregarTarea">
            <v-text-field
              name="name"
              label="Título de la Tarea"
              v-model="titulo"
              id="id"
              autofocus="true"
            ></v-text-field>
            <v-textarea label="Descripción de la Tarea" v-model="descripcion"></v-textarea>
            <v-btn color="success" block type="submit">Agregar Tarea</v-btn>
          </v-form>
        </v-card>
      </v-flex>
      <v-flex md6 v-if="!formAgregar">
        <v-card class="mb-3 pa-3">
          <v-form @submit.prevent="editarTarea">
            <v-text-field
              name="name"
              label="Título de la Tarea"
              v-model="titulo"
              id="id"
              autofocus="true"
            ></v-text-field>
            <v-textarea label="Descripción de la Tarea" v-model="descripcion"></v-textarea>
            <v-btn color="warning" block type="submit">Editar Tarea</v-btn>
          </v-form>
        </v-card>
      </v-flex>
      <v-flex md6>
        <v-card class="mb-3" v-for="(item, index) in listaTareas" :key="index">
          <v-card-text>
            <v-chip class="ml-0" color="pink" label text-color="white">
              <v-icon left>mdi-label</v-icon>
              {{item.titulo}}
            </v-chip>
            <p>{{item.descripcion}}</p>
            <v-btn color="warning" class="ml-0" @click="editar(index)">Editar</v-btn>
            <v-btn color="error" class="ml-2" @click="eliminarTarea(item.id)">Eliminar</v-btn>
          </v-card-text>
        </v-card>
      </v-flex>
    </v-layout>

    <v-snackbar v-model="snackbar" timeout="3000">
      {{ mensaje }}
      <v-btn dark text @click="snackbar = false">Cerrar</v-btn>
    </v-snackbar>

    <Footer />
  </v-container>
</template>


<script>
import NavBar from "@/components/NavBar.vue";
import Footer from "@/components/Footer.vue";

export default {
  components: {
    NavBar,
    Footer
  },
  data() {
    return {
      listaTareas: [
        {
          id: 1,
          titulo: "Titulo Tarea #1",
          descripcion:
            "Primer producto con las caracteristicas necesarias para llenar una buena cantidad de palabras que se asemeje a un descripcion"
        },
        {
          id: 2,
          titulo: "Titulo Tarea #2",
          descripcion:
            "Segundo producto con las caracteristicas necesarias para llenar una buena cantidad de palabras que se asemeje a un descripcion"
        }
      ],
      titulo: "",
      descripcion: "",
      snackbar: false,
      mensaje: "",
      formAgregar: true,
      indexTarea: ""
    };
  },
  methods: {
    agregarTarea() {
      console.log(this.titulo, this.descripcion);
      if (this.titulo === "" || this.descripcion === "") {
        this.snackbar = true;
        this.mensaje = "Llena todos los campos";
      } else {
        this.listaTareas.push({
          id: Date.now(),
          titulo: this.titulo,
          descripcion: this.descripcion
        });
        this.titulo = "";
        this.descripcion = "";
        this.snackbar = true;
        this.mensaje = "Tarea Agregada";
      }
    },
    eliminarTarea(id) {
      this.listaTareas = this.listaTareas.filter(e => e.id != id);
      this.snackbar = true;
      this.mensaje = "Tarea Eliminada";
    },
    editar(index) {
      this.formAgregar = false;
      this.titulo = this.listaTareas[index].titulo;
      this.descripcion = this.listaTareas[index].descripcion;
      this.indexTarea = index;
    },
    editarTarea() {
      this.listaTareas[this.indexTarea].titulo = this.titulo;
      this.listaTareas[this.indexTarea].descripcion = this.descripcion;
      this.formAgregar = true;
      this.titulo = "";
      this.descripcion = "";
      this.snackbar = true;
      this.mensaje = "Editaste la tarea";
    }
  }
};
</script>





