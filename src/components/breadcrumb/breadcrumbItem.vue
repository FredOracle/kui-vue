<template>
    <span class="k-breadcrumb-item">
        <span class="k-breadcrumb-link" @click="toPath">
            <Icon :type="icon" v-if="icon" />
            <slot></slot>
        </span>
        <span class="k-breadcrumb-separator">{{separator}}</span>
    </span>
</template>
<script>
import Icon from "../icon";
export default {
    components: { Icon },
    name: 'BreadcrumbItem',
    props: {
        separator: { type: String, default: '/' },
        to: String,
        replace: Boolean,
        icon: String
    },
    methods: {
        toPath() {
            this.to && this.replace ? this.$router.replace({ path: this.replace }) : this.$router.push({ path: this.to })
        }
    }
}
</script>
