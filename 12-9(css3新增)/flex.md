- 注意设为Flex布局之后，子元素的float clear和vertical-align属性将失效，而且pc端不一定兼容，移动端基本兼容
- 采用Flex布局的元素，他的索引子元素自动成为容器成员，称为Flex项目（Flex item），简称“项目”
- 容器默认两根轴，水平的主轴和垂直的交叉轴
- 属性
  - flex-direction：设置主轴的方向
    - row主轴的方向是水平的，从左到右（默认的）
    - row-reverse主轴的方向是水平的，从右到左
    - column主轴的方向是垂直的，从上到下
    - column-reverse主轴的方向是垂直的，从下到上
  - flex-wrap：设置是否换行
    - wrap：换行
    - nowrap：不换行（默认的）
    - wrap-reverse：换行，不过第一行在最下面
  - flex-flow属性是flex-direction和flex-wrap属性的简写 默认是row nowrap
  - justify-content：定义项目在主轴上的对齐方式
    - flex-start：开头（默认的）
    - flex-end：末尾
    - center：中间
    - space-between：两边挨着边框，中间均分
    - space-around：两边比中间的间距少一半
    - space-evenly：所有的间距均分
  - align-items：定义羡慕在交叉轴上的对齐方式
    - flex-start：开头
    - flex-end：末尾
    - center：中间
    - baseline：基线对齐
    - stretch：拉伸（默认值，注意如果项目没有设置高度或者设为auto，将沾满整个容器的高度）
  - align-content：定义多根轴线的对齐方式，如果项目只有一根轴线不起作用，（也就是说得有项目换行）
    - flex-start：开头
    - flex-end：结尾
    - center：中间
    - space-between：两边挨着边框，中间间距均分
    - space-around：两边的间距比中间的间距少一半
  - 项目的属性，写在自身上
    - order：定义了项目的排列顺序，数值越小，排列越靠前，默认为0
    - flex：给子集分配剩余的空间，按分数
    - align-self:允许单个项目有与其他项目不一样的对齐方式，可以覆盖align-items属性，默认值为auto，表示继承父元素的aligin-items属性，如果没有父元素，则等同于stretch
```
 <style>
    #box{
        height: 500px;
        width: 500px;
        background:red;
        display: flex;
    }
    div{
        height: 50px;
        width: 50px;
        border:1px solid black;
    }
    #box :nth-child(2){
        order: -1;
        flex:2;
        align-self:center
    }
    #box :nth-child(1),#box :nth-child(3){
        
        flex:1;
    }
    </style>
</head>
<body>
    <div id="box">
     <div>1</div>
     <div>2</div>
     <div>3</div>

    </div>
```