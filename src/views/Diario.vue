<template>
    <div>

        <mdb-container class="mt-4">
            <mdb-row>

                <mdb-col col="12" class="bg-white text-dark rounded-lg z-depth-3" 
                style="box-sizing: content-box;padding: 0;" >

                    <section class="bg-primary rounded-top">
                        <nav class="d-flex justify-content-between py-2 mx-3">
                            <div>
                                <span class="mx-2 font-weight-bold">Clima:</span>
                                <span><i class="fas fa-cloud"></i></span>
                            </div>
                            <div><span class="mx-2 font-weight-bold">00/00/0000</span></div>
                        </nav>
                    </section>

                    <!-- Aqui comienza el editor -->
                    <section id="editorjs" class="text-left"></section>

                    <section class="bg-primary rounded-bottom">
                        <button id="salvar">Salvar</button>
                    </section>
                </mdb-col>
            </mdb-row>
        </mdb-container>


    </div>
</template>


<script>
import {mdbContainer, mdbRow, mdbCol} from 'mdbvue';

/* 
    Para agregar funcionalidades al editor tuvimos que hacer
        npm install --save @editorjs/header @editorjs/list 
*/
import EditorJS from '@editorjs/editorjs';
import Header from '@editorjs/header';
import List from '@editorjs/list';
import Embed from '@editorjs/Embed';

export default {
    name : 'Diario',
    components:{
        mdbContainer,
        mdbRow,
        mdbCol,
    },
    data() {
        return {
            editorContent : [],
            fecha : '',
        }
    },
    methods: {
        cargarDatos(){
            this.editorContent = [
                 {
            type: "header",
            data: {
              text: "Editor.js",
              level: 2
            }
          },
          {
            type : 'paragraph',
            data : {
              text : 'Hey. Meet the new Editor. On this page you can see it in action — try to edit this text. Source code of the page contains the example of connection and configuration.'
            }
          },
          {
            type: "header",
            data: {
              text: "Key features",
              level: 3
            }
          },
          {
            type : 'list',
            data : {
              items : [
                'It is a block-styled editor',
                'It returns clean data output in JSON',
                'Designed to be extendable and pluggable with a simple API',
              ],
              style: 'unordered'
            }
          },
            ];
        }
    },
    //Este eveto es de Vue es el equivalente a onload de js vanilla
    mounted(){  
        this.cargarDatos();

        //Inicializamos el editor js
        var editor = new EditorJS({
            holder: 'editorjs',
            tools:{
                header:{
                    class:Header,
                    inlineToolbar:['link']
                },
                list: {
                    class:List,
                    inlineToolbar:[
                        'link',
                        'bold'
                    ]
                },
                embed:{
                    class: Embed,
                    inlineToolbar: false,
                    config: {
                        services:{
                            youtube: true,
                            coub : true,
                        }
                    }
                },

            },
            data: {
                /*Hacemos el enlace con vue al pasar nuestra variable desde el data de vue */
                blocks: this.editorContent
            }, 
            onChange: function() {
                //RECORDATORIO HACER CODIGO PARA ACTUALIZAR EN LA BD
                console.log('Actualizar en la BD');
            }

        });

        //Asignamos el guardado de la información
        document.getElementById('salvar').addEventListener('click',function(){
            editor.save().then((outputData)=>{
                console.log('Article data',outputData);
                this.editorContent = outputData.blocks;
            }).catch((error)=>{
                console.log('Saving failed: ',error);
            });
        });
    },

}
</script>

