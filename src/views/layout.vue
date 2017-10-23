<template>
    <div>
        <el-container class="layout">
            <el-header class="layout-header">
                <el-row :gutter="20">
                    <el-col :span="3">
                        <h1 class="logo">LOGO</h1>
                    </el-col>
                    <el-col :span="17">
                        <el-menu :default-active="headerMenuActiveIndex" mode="horizontal">
                            <el-menu-item index="1">首页</el-menu-item>
                            <el-submenu index="2">
                                <template slot="title">菜单二</template>
                                <el-menu-item index="2-1">选项1</el-menu-item>
                                <el-menu-item index="2-2">选项2</el-menu-item>
                                <el-menu-item index="2-3">选项3</el-menu-item>
                            </el-submenu>
                            <el-menu-item index="3">菜单三</el-menu-item>
                            <el-menu-item index="4">菜单四</el-menu-item>
                            <el-menu-item index="5">菜单五</el-menu-item>
                        </el-menu>
                    </el-col>
                    <el-col :span="4">
                        <div class="layout-header-right">
                            <el-dropdown placement="bottom">
                                <span class="el-dropdown-link">
                                admin <i class="el-icon-arrow-down el-icon--right"></i>
                                </span>
                                <el-dropdown-menu slot="dropdown">
                                    <el-dropdown-item>用户中心</el-dropdown-item>
                                    <el-dropdown-item divided>退出</el-dropdown-item>
                                </el-dropdown-menu>
                            </el-dropdown>
                        </div>
                    </el-col>
                </el-row>
            </el-header>
            <el-container>
                <el-aside class="layout-aside">
                    <el-button size="mini" class="aside-switch" @click="asideSwitch">
                        <i class="el-icon-d-arrow-left"></i>
                        <i class="el-icon-d-arrow-right"></i>
                    </el-button>
                    <el-menu default-active="1-4-1" class="layout-aside-menu" :collapse="isCollapse">
                        <el-submenu index="1">
                            <template slot="title">
                                <i class="el-icon-message"></i>
                                <span slot="title">导航一</span>
                            </template>
                            <el-menu-item-group>
                                <span slot="title">分组一</span>
                                <el-menu-item index="1-1">选项1</el-menu-item>
                                <el-menu-item index="1-2">选项2</el-menu-item>
                            </el-menu-item-group>
                            <el-menu-item-group title="分组2">
                                <el-menu-item index="1-3">选项3</el-menu-item>
                            </el-menu-item-group>
                            <el-submenu index="1-4">
                                <span slot="title">选项4</span>
                                <el-menu-item index="1-4-1">选项1</el-menu-item>
                            </el-submenu>
                        </el-submenu>
                        <el-menu-item index="2">
                            <i class="el-icon-menu"></i>
                            <span slot="title">导航二</span>
                        </el-menu-item>
                        <el-menu-item index="3">
                            <i class="el-icon-setting"></i>
                            <span slot="title">导航三</span>
                        </el-menu-item>
                    </el-menu>

                </el-aside>
                <el-container class="layout-container">
                    <el-main class="layout-main">
                        <router-view/>
                    </el-main>
                </el-container>
            </el-container>
        </el-container>

    </div>
</template>

<script>
    export default {
        data() {
            return {
                isCollapse: true,
                headerMenuActiveIndex: '1'
            };
        },
        methods: {
            asideSwitch() {
                this.isCollapse = !this.isCollapse;
            }
        }
    }
</script>

<style>

    .layout-aside-menu:not(.el-menu--collapse) {
        width: 200px;
        min-height: 400px;
    }

    .layout-box {
        border: 1px solid #e6ebf5;
        background-color: #fff;
        padding: 15px;
    }

</style>

<style scoped>
    .layout-header {
        border-bottom: solid 1px #e6e6e6;
    }

    .layout-header-right {
        margin: 20px 10px 0 0;
        float: right;
    }

    .layout-header-right .el-dropdown {
        cursor: pointer;
    }

    .logo {
        height: 60px;
        line-height: 60px;
        padding: 0 20px;
    }

    .layout-aside {
        width: auto !important;
        overflow: inherit;
    }

    .aside-switch {
        width: 100%;
        border-radius: inherit;
    }

    .layout-aside-menu {
        height: 100%;
    }

    .layout-container {
        background: #FAFAFA;
    }

    .layout-main {
        padding: 10px;
    }

</style>
