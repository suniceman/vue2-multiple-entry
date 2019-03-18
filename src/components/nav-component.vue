<template>
    <div class="nav-wrap">
        <ul class="nav-block">
            <li class="logo"><b>Suniceman</b></li>
            <li :class="{ current: current === 1 }">
                <a href="../index"><i></i>首页</a>
            </li>
            <li :class="{ current: current === 2 }">
                <a href="../login"><i></i>登录</a>
            </li>
            <li :class="{ current: current === 3 }">
                <a href="../module3"><i></i>模块3</a>
            </li>
            <li :class="{ current: current === 4 }">
                <a href="../router"><i></i>路由</a>
            </li>
            <li :class="{ current: current === 5 }">
                <a href="../vuex"><i></i>Vuex</a>
            </li>
        </ul>
    </div>
</template>
<script>
import '../assets/less/style.less'
export default {
    props: ['current']
}
</script>
