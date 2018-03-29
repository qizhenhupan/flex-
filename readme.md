# flex实现手风琴效果和圣杯三列布局，超简单
## accordion
    主要思路就是，使用flex的flex属性，实现自适应的grow和shrink
    当hover时，item放大，其它item根据flex属性自动缩小，实现手风琴拉拽效果。
    .item flex:1;
    .item:hover flex:35%;

## holy grail
    主要思路是使用order属性，使得排在最上面的main_content排在中间。
    html
        main_content
        left
        right
    css
        main_content order:1
        right order:1
        left (默认为0,排在最左侧)

# normal思路
## accordion
    主要思路：使用float排为一行，正常时item平分。
    当父容器hover，hover的子元素，宽度放大，非hover子元素减少。

    问题：由于放大和缩小的宽度不一致，导致整个容器不能充满。
    这是正常方案不如flex的最大原因。

## holy grail
    主要思路，float排为一行。
    left margin-left -100%
    right margin-left -200px
    center width 100%
            padding 0 200px
            box-sizing border-box
    使用margin-left -100%实现定位左侧。
