<template>
<div class= "totalPagina">
        <header class="navbar">
                        <section class="navbar-section">
                          <img class="img-responsive img-logo" src="@/assets/logo-learning-memory.png">
                        </section>
        </header>
                    <div class="column col-4 col-mx-auto "><h1>CADASTRO DE DISCIPLINA</h1>
                        <div class="container-dscpn">

                                <label class="form-label label-dscpn" for="input-example-1">Disciplina</label>
                                <input class="form-input input-dscpn" type="text" id="" placeholder="Nome da disciplina" v-model="disciplina">
                                <label class="form-label label-email" for="input-example-1">E-mail do Professor</label>
                                <input class="form-input input-email" type="text" id="" placeholder="E-mail do professor" v-model="emailProf">
                                <button v-on:click="cadastrar" type="button" class="btn btn-primy bg-dark btn-lg">Cadastrar</button>

                               <table class="table table-striped table-hover" >
                                        <thead>
                                            <tr>
                                            <th>Disciplina</th>
                                            <th>Email do Professor</th>
                                            </tr>
                                        </thead>
                                        <tbody>
                                            <tr class="active" v-for="cadastro in cadastros" :key="cadastro.id">
                                            <td>{{cadastro.disciplina}}</td>
                                            <td>{{cadastro.emailProf}}</td>
                                            </tr>
                                        </tbody>
                                </table>




                        </div>
                    </div>


</div>

</template>

<script>
export default {

    name: "cadastroDisciplina",

    data() {
        return{
            cadastros: [],
            disciplina: "",
            emailProf: "",
        }
    },
    methods: {
        cadastrar() {
            console.log('fdp')
            this.cadastros.push({
                disciplina: this.disciplina,
                emailProf: this.emailProf,
                id: Date.now()
            });

            this.disciplina = "",
            this.emailProf = ""

        }
    }



}
</script>

<style scoped>

            *{
                font-family: 'Roboto', sans-serif;
            }

            .img-logo {
            max-width: 200px;
            margin: 0 auto;
            }

            .navbar {
            width: 100%;
            background-color: #47525E;
            height: 100px;
            }

            .col-4 {
                text-align: center;
                height: 800px;
                margin-top: 50px;
                font-family:  'Roboto', sans-serif;
            }

            h1{
                font-size: 50px;
            }

            .container-dscpn{
                padding: 30px;
            }

            .label-dscpn{
                text-align: initial;
                font-family:  'Roboto', sans-serif;
                font-size: 20px;
                border-left: 8px solid #4fc08d;
            }
            .label-email{
                text-align: initial;
                font-family:  'Roboto', sans-serif;
                font-size: 20px;
                border-left: 8px solid #4fc08d;
                margin-top: 20px;

            }

            .btn {
                 margin-top: 30px;
                 border: none;
                }

                .table {
                    margin-top: 30px;
                }






</style>
