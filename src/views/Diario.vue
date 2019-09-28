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

                    <section id="texto">
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolor laudantium suscipit, autem explicabo expedita odit eligendi impedit ducimus ut similique voluptatem, numquam quisquam iure minus quasi deserunt quidem sint. Eos.
                    </section>

                    <section class="bg-primary rounded-bottom">
                        texto
                    </section>
                </mdb-col>
            </mdb-row>
        </mdb-container>


    </div>
</template>

<script>
import {mdbContainer, mdbRow, mdbCol} from 'mdbvue';
import EditorJS from '@editorjs/editorjs';
export default {
    name : 'Diario',
    components:{
        mdbContainer,
        mdbRow,
        mdbCol,
    }
}
</script>