<script>
import hljs from 'highlight.js';  // 代码高亮
import WeComponents from '../../../../src/';  // 引入组件库

let pageFields = [
    {
        value: '快速入门',
        attributes: {
            size: 'large',
            bold: true
        }
    },
    {
        value: '0. 安装',
        attributes: {
            size: 'medium',
            bold: true
        }
    },
    {
        component: 'html',
        value: `<pre><code>
    npm install --save @weadmin/wecomponents;
</code></pre>`
    },
    {
        value: '1. 引入WeComponents',
        attributes: {
            size: 'medium',
            bold: true
        }
    },
    {
        component: 'html',
        value: `<pre><code>
    import WeComponents from "@weadmin/wecomponents";
</code></pre>`
    },
    {
        value: '2. 声明页面所需组件',
        attributes: {
            size: 'medium',
            bold: true
        }
    },
    {
        component: 'html',
        value: `<pre><code>
    let pageFields = [
        {
            component: "input",
            label: '标题'
        }
    ];
`
    },
    {
        value: '3. 绑定组件声明',
        attributes: {
            size: 'medium',
            bold: true
        }
    },
    {
        component: 'html',
        value: `<pre><code>
    export default {
        data(){
            return {
                page: new WeComponents(this, pageFields)
            }
        }
    };
</code></pre>`
    },
    {
        value: '完整示例',
        attributes: {
            size: 'medium',
            bold: true
        }
    },
    {
        component: 'html',
        value: `<pre><code>
    import WeComponents from "@weadmin/wecomponents";

    let pageFields = [
        {
            component: "input",
            label: '标题'
        }
    ];

    export default {
        data(){
            return {
                page: new WeComponents(this, pageFields)
            }
        }
    };
</code></pre>`
    }
];


export default {
    name: 'v2Test',

    data() {
        return {
            // 初始化组件库
            page: new WeComponents(this, pageFields)
        };
    },

    mounted() {
        let codes = document.querySelectorAll('pre code');

        // 高亮代码
        codes.forEach(code => hljs.highlightBlock(code));
    }
};
</script>
