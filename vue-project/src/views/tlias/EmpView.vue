<template>
    <div>
        <el-container style="height: 500px; border: 1px solid #eee">
            <el-header style="font-size: 40px; background-color: rgb(238, 241, 246)">赋棠苑4-19人员管理系统</el-header>
            <el-container>
                <el-aside width="200px">
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

                    <!-- 表单 -->
                    <el-form :inline="true" :model="searchFrom" class="demo-form-inline">
                        <el-form-item label="姓名">
                            <el-input v-model="searchFrom.name" placeholder="姓名"></el-input>
                        </el-form-item>
                        <el-form-item label="性别">
                            <el-select v-model="searchFrom.gender" placeholder="性别">
                                <el-option label="男" value="1"></el-option>
                                <el-option label="女" value="2"></el-option>
                            </el-select>
                        </el-form-item>
                        <el-form-item label="入职日期">
                            <!-- 日期选择器 -->
                            <el-date-picker v-model="searchFrom.entrydate" type="daterange" range-separator="至"
                                start-placeholder="开始日期" end-placeholder="结束日期">
                            </el-date-picker>
                        </el-form-item>
                        <el-form-item>
                            <el-button type="primary" @click="onSubmit">查询</el-button>
                        </el-form-item>
                    </el-form>
                    <!-- 表格 -->
                    <el-table :data="tableData" border="1">
                        <el-table-column prop="name" label="姓名" width="180"></el-table-column>
                        <el-table-column label="图像" width="180">
                            <template slot-scope="scope">
                                <img :src="scope.row.image" width="100px" height="70px">
                            </template>
                        </el-table-column>
                        <el-table-column label="性别" width="140">
                            <template slot-scope="scope">
                                {{ scope.row.gender == 1 ? '男' : '女' }}
                            </template>
                        </el-table-column>
                        <el-table-column prop="job" label="职位" width="140"></el-table-column>
                        <el-table-column prop="entrydate" label="出生日期" width="180"></el-table-column>
                        <el-table-column prop="updatetime" label="学号" width="230"></el-table-column>
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
import axios from 'axios';
export default {
    data() {
        return {
            tableData: [],
            searchFrom: {
                name: "",
                gender: "",
                entrydate: []
            }
        }
    },
    methods: {
        onSubmit: function () {
            alert("查询数据");
        },
        handleSizeChange: function (val) {
            alert("每页记录数变化" + val)
        },
        handleCurrentChange: function (val) {
            alert("页码发生变化" + val)
        }

    },
    mounted() {
        //发送异步请求，获取数据
        axios.get("http://yapi.smart-xwork.cn/mock/238722/user/getByld").then((result) => {
            this.tableData = result.data.data;
        });
    }
}
</script>

<style></style>