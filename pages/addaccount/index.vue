<template>
    <div>
        <v-row class="d-block">
            <h4 class="pa-2 pt-4">Country</h4>
            <v-select
                class="pl-2 pr-2"
              :items="Country"
              label="Standard"
            ></v-select>
        </v-row>
        <v-row class="d-flex">
            <v-text-field
                color="#ffff"
                class="pl-2 pr-1 col-2"
                placeholder="+98"
                flat
                v-model="CountryCode"
            ></v-text-field>
             <v-text-field col-9 class="pr-2" v-model="PhoneNumber"
             type="number"
            label="Phone Number"
          ></v-text-field>
        </v-row>
        <v-row class=" pl-2 pr-2">
            <p class="message">We will send an SMS with a confirmation code to your phone number.</p>
        </v-row>
        <v-row v-show="submit" class="ma-2 justify-end" >
            <v-btn color="primary" fab dark  class="justify-center">
                <v-icon>mdi-arrow-right</v-icon>
            </v-btn>
        </v-row>
    </div>
</template>
<script>

export default ({
    layout:'addaccount',
    data(){
        return{
            CountryCode:null,
            PhoneNumber:null,
            submit:false,
            Country: ['Afghanestan', 'Iran', 'American Samoa', 'Algeria'],
        }
    },
    watch:{
        PhoneNumber:function(){
            this.PhoneNumber  ? this.submit = true : this.submit = false;
        }
    }
})
</script>
<style lang="scss" scoped>
.message {
    color: darkgray;
}

.submit-show{
    width: 65px;
    height: 65px;
    transition: 1s;
}
</style>
