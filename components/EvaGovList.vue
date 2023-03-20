<template>
   <v-list>
    <v-list-item v-on:click="govs" v-for="gov in govs">
        {{ gov.gov }} <br>
        {{ gov.data }}
    </v-list-item>
   </v-list>
</template>
<script>
export default {
    name: 'EvaGovNumber',
    data(){
        return {
            govs: [{gov: 1, dt: 2, id: 3}]
        };
    },
    created(){
        this.govs = JSON.parse(gov)
        // var ViewItem = [ "1" ];
        // var serialView = JSON.stringify(ViewItem);
        // localStorage.setItem("ViewItem1", serialView);
        // var returnView = JSON.parse(ViewItem);
        // this.govs=localStorage.getItem('evaGovNum');
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