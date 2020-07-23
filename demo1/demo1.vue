<template>
    <div>
        <ul>
            <li v-for="(item,index) in lists" :key="index" @click="choose(index)"
                :class="{active: index == current && current !== ''}">
                <!-- 或者 index===current 此时 add里不需要 this.current =  '' -->
                {{item}}
            </li>
        </ul>
        <button type="button" @click="add()">添加</button>
        <ul>
            <li v-for="(item,index) in target" :key="index">{{item}}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "demo1",
        data() {
            return {
                current: '',
                lists: [1, 2, 3, 4, 5, 6, 7, 8, 9],
                target: []
            }
        },
        methods: {
            choose(index) {
                this.current = index
            },
            add() {
                if (this.current == '') {
                    return
                }
                this.target.push(this.lists[this.current]),
                    this.current = ''
            }
        }
    }
</script>

<style scoped>
    li {
        list-style: none
    }

    li.active {
        background: rgb(240, 181, 72);
    }

    button {
        background-color: #fff;
        border: solid 1px rgb(240, 181, 72);
    }
    button:hover {
        background-color: rgb(240, 181, 72);
        color: #fff;
    }
</style>