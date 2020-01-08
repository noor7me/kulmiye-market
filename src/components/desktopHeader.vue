<template>
    <v-app-bar
        app
        color="primary"
        dark
        flat
        dense
        
    >
    <div class="d-flex align-center">
        <v-img
            alt="Kulmiye Market Logo"
            class="shrink mr-2"
            contain
            src="/logo.JPG"
            transition="scale-transition"
            width="60"
        >
        </v-img>
       
    </div>
    <div class="menu-box"    
    
        v-if="!searchOn" >
        <v-tabs
            background-color="white"
            color="secondary"
            align-with-title
            light
            show-arrows
        >
            <v-tab>
                <strong>Electronics</strong>
            </v-tab>
            <v-tab>
                <strong>Gawaari </strong>
            </v-tab>
            <v-tab>
                <strong>Qalabka Guryaha </strong>
            </v-tab>
            <v-tab>
                <strong>...... </strong>
            </v-tab>
            <v-tab>
                <strong>...... </strong>
            </v-tab>
            <v-tab>
                <strong>...... </strong>
            </v-tab>

        </v-tabs>  
    </div>
    <div v-if="searchOn" class="search-box"> 
        <v-text-field

            v-model="message"
            outlined
            filled
            
            autofocus
            solo-inverted
            
            dense
            flat
            clearable
            label="Ka raadi suuqa kulmiye"
            type="text"
            color="secondary"
            prepend-inner-icon="mdi-magnify"

            @click:clear="onClose()"
            @click:prepend-inner="onClose()"
            @keyup.enter="searchOn = !searchOn" 
               
        >
        </v-text-field>
    </div>

    <v-spacer></v-spacer>
    
    <v-btn icon class="magnify-icon-box">
        <v-icon color="secondary"
            @click="searchOn = !searchOn"
        >mdi-magnify</v-icon>
    </v-btn>

    <v-btn icon>
        <v-icon color="secondary">mdi-camera</v-icon> 
       <span class="secondary--text">iibi</span>
    </v-btn>
    <div class="iibgee-box">

    </div>

    </v-app-bar>
</template>

<script>
export default {
    name: 'desktopHeader',
    data() {
        return {
            searchOn: false,
            message: "",
            loading: false,
            isActive: false

        }
    }, 
    methods: {
        clickMe()   {
            this.loading    = true,
            this.message    =   "wait for it"
            setTimeout(() => {
                this.loading    =   false,
                this.message    = " i am done !!!"
            }, 2000)
        },
        clickMe2() {
            this.searchOn = false
        },

        onClose() {
            this.searchOn = !this.searchOn; //close the search box 
            this.message  = "";              // empty the search box 
        }
    }
    
}
</script>

<style scoped>
    .search-box{
        margin-left: 300px;
        margin-top: 30px;
        width: 800px;
        border-radius: 120px;
    }
    .menu-box{
        margin-left: 60px;
    }
    .magnify-icon-box{
        margin-right: 50px;
    }
    .iibgee-box{
        margin-right: 30px;
    }

</style>