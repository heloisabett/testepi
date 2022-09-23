<script>
  import axios from "axios";
  export default {
    data() {
      return {
        cep: "",
        endereco: {},
      };
    },
    methods: {
      async buscar() {
        const url = `https://viacep.com.br/ws/${this.cep}/json/`;
        const { data } = await axios.get(url);
        this.endereco = data;
      },
    },
  };
  </script>
  
  <template>
    <div class="caixa">
      <div>
        <h1>Buscar CEP</h1>
        <form @submit.prevent="buscar" class="form1">
          <label>CEP</label>
          <input type="text" v-model="cep" />
          <button type="submit">Buscar</button>
        </form>
        <form class="form2">
          <label for="rua">Rua</label>
          <input name="rua" type="text" v-model="endereco.logradouro" />
          <label for="numero">Número</label>
          <input name="numero" type="text" v-model="endereco.numero" />
          <label for="complemento">Complemento</label>
          <input name="complemento" type="text" v-model="endereco.complemento" />
          <label for="bairro">Bairro</label>
          <input name="bairro" type="text" v-model="endereco.bairro" />
          <label for="localidade">Cidade</label>
          <input name="cidade" type="text" v-model="endereco.localidade" />
          <label for="uf">Estado</label>
          <input name="estado" type="text" v-model="endereco.uf" />
        </form>
      </div>
    </div>
  </template>
  
  <style scoped>
  .form1 {
    width: 200px;
    height: 90px;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    border: 1px solid lightgrey;
    background-color: rgba(207, 190, 211, 0.719);
    border-radius: 7px;
  }
  h1{
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;

  }
  .form2 {
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    width: 200px;
    height: 300px;
    border: 1px solid lightgray;
    background-color: rgba(207, 190, 211, 0.719);
    border-radius: 7px;
  }
  input {
    border: 1px solid rgb(148, 102, 160);
    align-self: center;
    border-radius: 7px;
  }
  button {
    border: 1px solid rgba(207, 190, 211, 0.719);
    background-color: rgba(236, 253, 247, 0.918);
    width: 60px;
    height: 30px;
    margin: 10px 65px;
    border-radius: 5px;
  }
  .caixa {
    display: flex;
    justify-content: center;
    background-color: rgba(228, 219, 233, 0.719);
    font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    height: 950px;
    width: 1905px;
    align-items: center;
    border-radius: 10px;

  }
  </style>