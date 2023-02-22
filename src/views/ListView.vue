<script>
export default {
    name: 'ListView',
    //declare data
    data:()=>({
        list:[
        {
            name: 'List Pertama'
        },
        {
            name: 'List Kedua'
        }
        ],
        //input data
        input: {
            name: ''
        }
    })
}
</script>
<template>
    <div>
        <h1>This is a list page</h1>

        <input type="text" v-model="input.name" placeholder="Input Name">

        <ol>
            <template v-for ="(item,index) in list" :key="index">
                <li>
                    {{item.name}}
                </li>
            </template>
        </ol>
    </div>
</template>
<style>

</style>
