<template>
    <div :class="{'small-icon-menu': true, 'column': column, 'border': border, 'absolute': absolute}" :style="menuStyle">
        <slot name="prepend"></slot>
        <template v-if="icons.length > 0">
            <i v-for="icon in icons" :key="icon" :class="['icon','material-icons', icon]" :style="iconStyle" @click.stop="$emit(icon)">{{ icon }}</i>
        </template>
        <slot></slot>
    </div>
</template>
<style scoped>
.small-icon-menu {
    position:relative;
    display: flex;
    flex-wrap: nowrap;
    text-align: center;
    justify-content: center;
    align-items: center;
    padding: 2px;
}
.small-icon-menu.absolute {
    position:absolute;
}
.small-icon-menu.border {
    border: 1px solid #ccc;
}
.small-icon-menu.column {
    flex-direction: column;
}
.small-icon-menu.row {
    flex-direction: row;
}
.small-icon-menu > .icon:last-child {
    margin: 0px !important;
}
.small-icon-menu > .icon {
    cursor: pointer;
    color: rgba(0,0,0,0.54);
    transition: 0.3s cubic-bezier(0.25, 0.8, 0.5, 1);
}
.small-icon-menu > .icon:hover {
    color:#2196f3;
}
</style>

<script>
export default {
    name: "SmallIconMenu",
    computed: {
        iconStyle: function() {
            var margin = '0 6px 0 0';
            if (this.column) {
                margin = '0 0 6px 0'; 
            } 
            return { 
                fontSize: this.iconSize, 
                margin: margin 
            };
        },
        menuStyle: function() {
            return { 
                top: this.top, 
                left: this.left, 
                width: this.width, 
                height: this.height 
            };
        }
    },
    props: {
        column: {
            type: Boolean,
            default: false
        },
        border: {
            type: Boolean,
            default: false
        },
        absolute: {
            type: Boolean,
            default: false
        },
        top: {
            type: String,
            default: '0px'
        },
        left: {
            type: String,
            default: '0px'
        },
        width: {
            type: String,
            default: 'auto'
        },
        height: {
            type: String,
            default: 'auto'
        },
        icons: {
            type: Array,
            default: () => ['add', 'delete', 'edit']
        },
        iconSize: {
            type: String,
            default: '16px'
        }
    }
};
</script>