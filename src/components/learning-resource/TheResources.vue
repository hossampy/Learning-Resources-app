<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resources')" :mode="storedResButtonMode">Stored
            Resources</base-button>
        <base-button @click="setSelectedTab('add-resource')" :mode="addResButtonMode">Add Resource</base-button>
    </base-card>

    <keep-alive>
        <component :is="selectedTab"></component>
    </keep-alive>
</template>

<script>
import StoredResources from './StoredResources.vue';
import AddResource from './AddResource.vue';

export default {
    components: {
        StoredResources,
        AddResource,
    },
    data() {
        return {
            selectedTab: 'stored-resources',
            storedResources: [
                {
                    id: 'official-guide',
                    title: 'Official Guide',
                    description: 'The official Vue.js documentation.',
                    link: 'https://vuejs.org',
                },
                {
                    id: 'google',
                    title: 'Google',
                    description: 'Learn to google...',
                    link: 'https://google.org',
                },
            ],
        };
    },
    provide() {
        return {
            resources: this.storedResources,
            Addresource: this.AddResource,
            RemoveResource: this.removeResource

        };
    },
    computed: {
        storedResButtonMode() {
            return this.selectedTab === 'stored-resources' ? null : 'flat';
        },
        addResButtonMode() {
            return this.selectedTab === 'add-resource' ? null : 'flat';
        },
    },
    methods: {
        setSelectedTab(tab) {
            this.selectedTab = tab;
        },
        AddResource(title,desc,url){
            const newResource = {
                id:new Date().toDateString,
                title:title,
                description:desc,
                link:url
            }
            this.storedResources.unshift(newResource)
            this.selectedTab ='stored-resources'
        },
        removeResource(resid){
            const Resourceindex = this.storedResources.findIndex(res => res.id === resid );
            this.storedResources.splice(Resourceindex,1)
        }
    },
};
</script>