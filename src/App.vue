<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Filters & Mixins</h1>
                <!-- Exercise 1) -->
                <!-- Build a local Filter which reverses the Text it is applied on -->
                <p>{{'my text' | reverseString}}</p>

                <!-- Exercise 2 -->
                <!-- Build a global Filter which counts the length of a word and it appends it -->
                <!-- Like this: "Test" => Gets Filtered to => "Test (4)" -->
                <p>{{'test' | caclLength}}</p>

                <!-- Exercise 3 -->
                <!-- Do the same as in Exercises 1 & 2, now with Computed Properties -->
                <p>{{reverse}}</p>
                <p>{{calclength}}</p>

                <!-- Exercise 4 -->
                <!-- Share the Computed Property rebuilding Exercise 2 via a Mixin -->
                <p>{{name}}</p>

            </div>
        </div>
    </div>
</template>

<script>
    import {data} from "./mymixin";

    export default {
        mixins: [data],
        data(){
            return{
                string: "template string"
            }
        },
        filters:{
            reverseString(value){
                return value.split("").reverse().join("");
            }
        },
        computed:{
            reverse(){
                return this.string.split("").reverse().join("");
            },
            calclength(){
                return this.string + " ("+ this.string.length + ")"
            }
        }
    }
</script>

<style>
</style>
