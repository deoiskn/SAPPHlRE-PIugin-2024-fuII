<script>
export default {
    name: 'ListView',
    data:()=>({
        list:[{
            name: 'List Pertama'
        },
    {
        name: 'List Kedua'
    }
    ]
    })
}
</script>
<template>
    <div>
        <h1>This is a list page</h1>
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
