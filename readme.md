# 项目说明

本项目作为样例代码，演示如何在网页中嵌入 GeoGebra 并用脚本创建内容。

# 参考资料

[GeoGebra - Scripting](https://wiki.geogebra.org/en/Scripting)

[GeoGebra - Scripting Commands](https://wiki.geogebra.org/en/Scripting_Commands)

[GeoGebra - All Commands](https://wiki.geogebra.org/en/Category:Commands)

[GeoGebra Apps Embedding](https://wiki.geogebra.org/en/Reference:GeoGebra_Apps_Embedding)

[GeoGebra App Parameters](https://wiki.geogebra.org/en/Reference:GeoGebra_App_Parameters)

# 常用指令

- 创建基本图形对象
```
O: (0, 0)
A: (1, 2)
B: (5, 1)

AB: Segment(A, B)
OA: Line(O, A)
OB: Ray(O, B)

f: y = sin(x)
g(x) = x^2 + 2x +1
h: (x-3)^2 + (y+2)^2 = 16

# https://wiki.geogebra.org/en/Circle_Command
c1: Circle(O, A)
```

- 设置图形对象属性
```
# https://wiki.geogebra.org/en/SetPointSize_Command
SetPointSize(O, 3)

# https://wiki.geogebra.org/en/SetPointStyle_Command
SetPointStyle(O, 10)

# https://wiki.geogebra.org/en/SetFixed_Command
SetFixed(O, true)

# https://wiki.geogebra.org/en/ShowLabel%20Command
ShowLabel(O, true)

# https://wiki.geogebra.org/en/SetLineThickness_Command
SetLineThickness(c1, 2)

# https://wiki.geogebra.org/en/SetLineStyle_Command
SetLineStyle(c1, 2)

# https://wiki.geogebra.org/en/SetColor_Command
SetColor(c1, "blue")

# https://wiki.geogebra.org/en/SetFilling_Command
SetFilling(c1, 0.3)
```

- 取点
```
# 取中点 https://wiki.geogebra.org/en/Midpoint_Command
P = Midpoint(AB)

# 取对称点 https://wiki.geogebra.org/en/Reflect_Command
Q = Reflect(O, AB)

# 取交点 https://wiki.geogebra.org/en/Intersect_Command
S = Intersect(f, c1, 1)

# 在给定的图形对象上取点，并设定其（最接近的）位置
C = Point(c1)
SetValue(C, (3, 1))
```

- 从一点向一直线做垂线
```
A: (5, 5)
l: y = x/3
B: Intersect(PerpendicularLine(A, l), l)
h: Segment(A, B)
  SetLineStyle(h, 2)
  SetLineThickness(h, 2)
```
