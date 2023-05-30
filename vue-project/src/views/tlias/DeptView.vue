<template>
    <div>
        <el-container style="height: 700px; border: 1px solid #eee">
            <el-header style="font-size:40px; background-color: rgb(238, 241, 246)">赋棠苑4-19人员管理系统</el-header>
            <el-container>
                <el-aside width="230px" style="border: 1px solid #eee">
                    <el-menu :default-openeds="['1', '3']">
                        <el-submenu index="1">
                            <template slot="title"><i class="el-icon-message"></i>系统信息管理</template>
                            <el-menu-item index="1-1">
                                <router-link to="/dept">床位管理</router-link>
                            </el-menu-item>
                            <el-menu-item index="1-2">
                                <router-link to="/emp">小弟管理</router-link>
                            </el-menu-item>
                        </el-submenu>
                    </el-menu>
                </el-aside>


                <el-main>
                    <!-- 表格 -->
                    <el-table :data="tableData" border>
                        <el-table-column prop="name" label="名称" width="250"></el-table-column>
                        <el-table-column prop="updatetime" label="学号" width="250"></el-table-column>
                        <el-table-column label="操作">
                            <el-button type="primary" size="mini">编辑</el-button>
                            <el-button type="danger" size="mini">删除</el-button>
                        </el-table-column>
                    </el-table>
                </el-main>
            </el-container>
        </el-container>
    </div>
</template>

<script>
export default {
    data() {
        return {
            tableData: [{
                id: 1,
                name: "1号床",
                updatetime: "202158914225"
            }, {
                id: 2,
                name: "2号床",
                updatetime: "202158914225"
            }, {
                id: 3,
                name: "3号床",
                updatetime: "202158914232"
            }, {
                id: 4,
                name: "4号床",
                updatetime: "202158914236"
            }, {
                id: 5,
                name: "5号床",
                updatetime: "202158914215"
            }, {
                id: 6,
                name: "6号床",
                updatetime: "202158914238"
            }]
        }
    },
    methods: {

    }
}
</script>

<style></style>