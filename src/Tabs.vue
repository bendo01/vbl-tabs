<template>
    <div>
        <div class="tabs" :class="predefinedClass">
            <ul>
                <li v-for="tab in tabs" :class="{ 'is-active': tab.isActive }">
                    <a :href="tab.href" @click.prevent="selectTab(tab)">{{ tab.name }}</a>
                </li>
            </ul>
        </div>
        <div class="tabs-details">
            <slot></slot>
        </div>
    </div>
</template>
<script>
'use strict';
import Vue from 'vue';
import Tab from './Tab'
export default {
    data () {
        return {
            tabs: []
        }
    },
    props: {
        predefinedClass: {
            type: String,
            default: ''
        }
    },
    mounted() {
        this.tabs = this.$children;
    },
    methods: {
        selectTab(selectedTab) {
            this.tabs.forEach(tab => {
                tab.isActive = (tab.href == selectedTab.href);
            });
        }
    }
}
</script>
