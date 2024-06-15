"1 & 2" is short for {1-1, 1-2, 1-3} & {2-1, 2-2, 2-3, 2-4}

'一些复习笔记

'1如果要画一个转动角度为45°的实心红色扇形

Dim r = 50
'扇形半径，50个像素

Dim rect As New Rectangle(x0 - r, y0 - r, 2 * r, 2 * r)
'注意rect是圆的外接正方形，所以长宽是2 * r而不是r；另外以(x0, y0)为圆心，所以起点坐标是(x0 - r, y0 - r).

g.FillPie(Brushes.Red, rect, 0, -45)
'学到两件事：1描述转动角度时我以为要写成PI/4（弧度制），没想到这个参数用的竟然是角度制；2没想到转动方向这里，也要注意y轴方向问题，所以不能写45而要写成-45

'2如果要绘制上半圆（上方是圆弧，下方为水平直线）

g.DrawPie(Pens.Blue, rect, 180, 180)
'万万没想到答案是这个，为啥啊

g.DrawPie(p, rec, 0, 180)
'这个很明显是错的，应该是0, -180

g.DrawPie(p, r, 180, 360)
'这个错了，为什么呢……哦哦哦，最后一个参数，这个角度描述的不是终边位置，而是要转多少度啊，原来如此！

'3Select Case语句的使用
'难以置信，期中刚刚新学的知识，期末就全忘了，这就是月抛式学习吗

Select Case x
    Case 90 to 100
        Msgbox("优")
    Case 80 to 90
        Msgbox("良")
End Select

Select Case x
    Case Is >= 90
        Msgbox("优")
    Case Is >= 80
        Msgbox("良")
End Select

Select Case x
    Case 10, 25, 34
        Msgbox("127.0.0.1")
    Case 137, 77 to 88, Is < 0
        Msgbox("It's raining cats and dogs.")
    Case "A" to "Z", "a" to "z"
        Msgbox("Traveller")
End Select
