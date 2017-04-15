<template>
    <div v-show="isActive"><slot></slot></div>
</template>
<script>
'use strict';
import Vue from 'vue';
export default {
    data() {
        return {
            isActive: false
        };
    },
    props: {
        name: {
            type: String,
            default: false
        },
        selected: {
            type: Boolean,
            default: false
        }
    },
    computed: {
        href() {
            return '#' + this.name.toLowerCase().replace(/ /g, '-');
        }
    },
    mounted() {
        this.isActive = this.selected;
    }
}
</script>
