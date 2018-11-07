<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12">
                <br>
                <button class="btn btn-primary" @click="switchComponent('app-blue')">Load Blue Template</button>
                <button class="btn btn-success" @click="switchComponent('app-green')">Load Green Template</button>
                <button class="btn btn-danger" @click="switchComponent('app-red')">Load Red Template</button>
                <hr>
                <component
                  :is="currentComponent">
                  <h1 slot="title">Title</h1>
                  <p>{{ componentsData[currentComponent] }}</p>
                </component>
            </div>
        </div>
    </div>
</template>

<script>
    import Blue from './components/Blue.vue';
    import Green from './components/Green.vue';
    import Red from './components/Red.vue';

    export default {
        data() {
            return {
                currentComponent: 'app-blue',
                componentsData: {
                    'app-blue': 'The content of blue component',
                    'app-green': 'The content of green component',
                    'app-red': 'The content of red component',
                }
            };
        },
        components: {
            appBlue: Blue,
            appGreen: Green,
            appRed: Red
        },
        methods: {
            switchComponent(selectedComponentName) {
                this.currentComponent = selectedComponentName;
            }
        }
    }
</script>

<style>
</style>
