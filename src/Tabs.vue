<template>
    <div>
        <div class="tabs">
            <ul>
                <li v-for="tab in tabs"><a href="#">{{tab.name}}</a></li>
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
export default {
    data () {
        return {
            tabs: []
        }
    },
    created() {
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
