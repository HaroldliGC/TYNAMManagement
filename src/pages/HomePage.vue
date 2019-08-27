<template>
    <div class="HomePage">
        <table cellspacing=0>
            <tr id="title">
                <td colspan="2">
                    <h1>TYNAM后台管理系统</h1>
                </td>
            </tr>

            <tr>
                <!-- menu start -->
                <td id="menu">
                    <div class="active">
                        <h4>主&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;页</h4>
                    </div>
                    <div>
                        <h4>关&nbsp;于&nbsp;我&nbsp;们</h4>
                    </div>
                </td>
                <!-- menu end -->
                <!-- data start -->
                <td id="container" class="show">
                    <h1>主页</h1>
                    <div id="searchArea">
                        姓名<input type="text" id="search-input">
                        <input type="button" class="btn search" value="检索">
                    </div>
                    <div id="btnArea">
                        <button class="btn" id="del">删除</button>
                        <button class="btn" id="edt">编辑</button>
                        <button class="btn" id="add">添加</button>
                    </div>
                    <div id="dataArea">
                        <table cellspacing=0>
                            <tr class="header">
                                <td class="code">学 号</td>
                                <td class="name">姓 名</td>
                                <td class="sex">性 别</td>
                                <td class="grader">年 级</td>
                            </tr>
                            <tr v-for="(data, index) in dataList" :key="index">
                                <td class="code">{{data.code}}</td>
                                <td class="name">{{data.name}}</td>
                                <td class="sex">{{data.sex}}</td>
                                <td class="grader">{{data.grader}}</td>
                            </tr>
                        </table>

                        <div id="del-dialog">
                            <div class="header">删除</div>
                            <div class="text"></div>
                            <button id="confirm">确定</button>
                            <button id="concel">取消</button>
                        </div>
                        <div id="add-dialog">
                            <div class="header">添加</div>
                            <div>学号<input type="text" class="code" maxlength="8" required></div>
                            <div>姓名<input type="text" class="name" max="8" required></div>
                            <div>性别<input type="text" class="sex" maxlength="1"></div>
                            <div>年级<input type="text" class="grader" maxlength="10"></div>
                            <button id="confirm">确定</button>
                            <button id="concel">取消</button>
                        </div>
                    </div>
                </td>
                <!-- data end -->
                <td id="about">
                    <h1>关于我们</h1>
                    <div class="container">
                        <P>TYNAM后台管理系统 用于学习。
                        </P>
                    </div>
                </td>
            </tr>

            <tr>
                <td colspan="2" id="coperight">
                    Copyright © 2019 Tynam</td>
            </tr>
        </table>
    </div>
</template>

<script>
export default {
    name: 'HomePage',
    data: function(){
        return {
            dataList: [
                {
                    id: 1,
                    code: 30001,
                    name: '段瑞琦',
                    sex: '男',
                    grader: '三年级二班'
                },
                {
                    id: 2,
                    code: 40002,
                    name: '韩子萱',
                    sex: '女',
                    grader: '四年级二班'
                },
                {
                    id: 3,
                    code: 20101,
                    name: '严寒',
                    sex: '男',
                    grader: '二年级一班'
                },
                {
                    id: 4,
                    code: 60012,
                    name: '钱小龙',
                    sex: '男',
                    grader: '六年级六班'
                }
            ]
        }
    }
}
</script>>

<style scoped>
* {
    margin: 0;
    padding: 0;
}

html,
body {
    width: 100%;
    height: 100%;
}

body table {
    width: 80%;
    min-width: 800px;
    max-width: 1200px;
    margin: 0 auto;
    border: 0;
    height: 98%;
    min-height: 800px;
    background-color:#eee;
}

/* title */
#title {
    background-color:#000;
    color: #eee;
    height: 70px;
}
#title h1 {
    margin-left: 40px; 
}

/* menu */
#menu {
    background-color: #3ca7ed;
    width: 20%;
    vertical-align: top;
    height: 70%;
    color: #eee;
}

#menu div.active {
    background-color: #eee;
    color: #333;
}

#menu div {
    margin-top: 5px;
    margin-left: 5px;
    padding: 20px;
}

/* container */
#container,
#about {
    display: none;
    vertical-align: top;
    padding: 20px;
}

.show {
    display: block !important;
}

/* about */
#container h1,
#about h1 {
    margin: 10px 10px;
    color: rgb(34, 33, 33);
}

/* 检索 */
#searchArea,
#about .container {
    margin-left: 10px;
    height: 50px;
    font-size: 16px;
    float: left;
}

#searchArea input {
    height: 25px;
    margin-left: 10px;
    padding: 0 4px;
}

/* btn */
#btnArea {
    height: 50px;
    margin: 50px 5px -10px 50px;  
}

#btnArea .btn,
#searchArea .btn {
    height: 30px;
}

#btnArea .btn,
#searchArea .btn {
    width: 80px;
    height: 30px;
    background: #3ca7ed;
    color: aliceblue;
    font-size: 16px;
    outline: none;
    border-style: none;
    float: right;
    margin: 0 10px;
}

#btnArea .btn:hover,
#searchArea .btn:hover,
#del-dialog button:hover,
#add-dialog button:hover {
    background: #0a84d4;
}

/* data */
#dataArea table {
    width: 98%;
    border-collapse: collapse;
    min-height: auto;
    overflow: scroll;
}

#dataArea tbody .code,
#dataArea table .name,
#dataArea table .sex,
#dataArea table .grader{
    width: 25%;
    height: 40px;
    line-height: 40px;
    text-align: center;
}

#dataArea tbody tr:nth-child(even) {
    background: aliceblue;
}

#dataArea tbody tr:nth-child(odd) {
    background: rgba(230, 239, 249);
}

#dataArea tbody tr.active {
    background: rgb(170, 207, 247);
}

#dataArea .header {
    background: #3ca7ed !important;
    color: aliceblue;
}

/* dialog */
#del-dialog,
#add-dialog {
    display: none;
    margin: 50px 15%;
    width: 400px;
    height: 150px;
    position: absolute;
    top: 150px;
    background: #fff;
    text-align: center;
    line-height: 65px;
    font-size: 18px;
}

#add-dialog {
    height: 270px;
}
#add-dialog div {
    height: 40px;
}

#add-dialog div input {
    width: 200px;
    padding: 3px 5px;
    margin: 5px 15px;
}

#del-dialog .header,
#add-dialog .header {
    background: #3ca7ed;
    color: aliceblue;
    height: 35px;
    text-align: left;
    padding-left: 10px;
    line-height: 35px;
}

#del-dialog button,
#add-dialog button {
    display: inline-block;
    width: 50px;
    height: 30px;
    background: #3ca7ed;
    outline: none;
    color: #f9f9f9;
    border-style: none;
    position: absolute;
    bottom: 15px;
    right: 25px;
}

#add-dialog #confirm,
#del-dialog #confirm {
    right: 85px;
}

/* coperight */
#coperight {
    background: #fff;
    color: #333;
    text-align: center;
    height: 5%;
}
</style>