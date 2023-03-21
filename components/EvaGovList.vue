<template>
   <v-list>
    <v-list-item v-on:click="govs" v-for="gov in govs">
        123 <br>
        {{ gov.gov }} <br>
        {{ gov.data }}
    </v-list-item>
   </v-list>
</template>
<script>
let gov = 8;
let n = 5;
let data = 6;
let idgov = 7;
export default {
    name: 'EvaGovNumber',
    data(){
        return { 
            govs: [{gov:(n), dt:(data), id:(idgov)}]
        };
    },
    created(){
        this.govs = JSON.parse(gov)
    },
    methods:{
        go(gov){
            localStorage.setItem('GovNum', JSON.stringify(govs))
            gov.dt = new Date();
            console.log(gov.dt);
            JSON.setItem('govs', JSON.stringify(this.govs))
            this.$emit('go',gov)
        }
    }
}
</script>