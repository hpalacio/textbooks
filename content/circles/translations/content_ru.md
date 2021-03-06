# Круги и Пи 

## Введение 

> section: introduction
> id: intro

::: column.grow

 Пока люди существуют, мы смотрели на небо и пытались объяснить жизнь на Земле, используя движение звезд, планет и луны. 

 Древнегреческие астрономы первыми обнаружили, что все небесные объекты движутся по регулярным путям, называемым __орбитами__ . Они считали, что эти орбиты всегда круговые. В конце концов, круги являются «наиболее совершенными» из всех форм: симметричными во всех направлениях и, следовательно, подходящим выбором для основного порядка нашей вселенной. 

::: column(width=320)

    x-img(src="images/geocentric.jpg" width=320 height=272)

{.caption} Земля находится в центре _вселенной Птолемеев_ . 

:::

---
> id: radius
> goals: compass

 Каждая точка на [__круге__](gloss:circle) имеет одинаковое расстояние от его центра. Это означает, что их можно нарисовать с помощью [компаса](gloss:compass) : 

::: column(width=320)

    x-geopad(width=320 height=300 style="position: relative;")
      svg(style="stroke-linecap: round; stroke-linejoin: round")
        circle.move(name="a" cx=160 cy=150 target="r d")
        circle.move.reveal(name="b" cx=250 cy=240 project="circle(a, 120)" target="r" when="compass")
        path.red(x="segment(a,b).contract(0.08)" target="r" arrows="both" hidden)
        path(name="c1" x="arc(a,b,1.99*pi)" hidden)
        path.blue(x="segment(b.rotate(pi/3,a),b.rotate(-2*pi/3,a)).contract(0.01)" target="d" arrows="both" hidden)
        path.green(x="arc(a,b.add(b.subtract(a).unitVector.scale(12)),1.99*pi).contract(0.02)" target="c" arrows="start" hidden)
      x-play-btn

::: column.grow

{.reveal(when="compass")} Есть три важных измерения, связанных с кругами, которые вам нужно знать: 

 * {.reveal(when="compass" delay="1000")} [{.pill.red.b} радиус](target:r) - это расстояние от центра круга до его внешнего обода. * {.reveal(when="compass" delay="4000")} [{.pill.blue.b} диаметр](target:d) - это расстояние между двумя противоположными точками на окружности. Он проходит через свой центр, и его длина в [[два раза | половина | такой же, как]] радиус. * {.reveal(when="blank-0")} [{.pill.green.b} окружность](target:c) (или периметр) - это расстояние вокруг круга. 

:::

---
> id: similar
> goals: circle-0 circle-1 circle-2

 Одним из важных свойств кругов является то, что все круги [похожи](gloss:similar) . Вы можете доказать это, показав, как можно сопоставить все круги, используя простые [переводы](gloss:translation) и [расширения](gloss:dilation) : 

    figure: svg.similar-circles(width=640 height=380 viewBox="0 0 640 380")

---
> id: pi-definition
> goals: digits

 Возможно, вы помните, что для аналогичных полигонов соотношение между соответствующими сторонами всегда постоянное. Нечто подобное работает для кругов: соотношение между [окружностью](gloss:circle-circumference) и [диаметром](gloss:circle-diameter) одинаково для _всех кругов_ . Это всегда 3.14159… - загадочное число, называемое [__Pi__](gloss:pi) , которое часто пишется как греческая буква _π_ для «p». У Пи бесконечно много десятичных цифр, которые продолжаются вечно без какого-либо определенного шаблона: 

    canvas.pi-spiral(width=800 height=760)

---
> id: wheel
> goals: unroll

 Вот колесо диаметром 1. Когда вы «раскатываете» окружность, вы можете видеть, что ее длина точно [[`pi`|`2 * pi`| 3]] : 

    figure: include svg/wheel.svg
    x-gesture(target="#wheel .wheel" slide="100,0")

---
> id: circumference

 Для круга диаметром _d_ длина окружности равна `C = π × d` , Аналогично, для круга с [радиусом](gloss:circle-radius) _r_ длина окружности равна 

{.text-center}`C =` [[`2 π r`|`π r`|`π r^2`]] , 

---
> id: nature

 Круги абсолютно симметричны, и у них нет «слабых мест», таких как углы многоугольника. Это одна из причин, почему их можно найти повсюду в природе: 

::: column(width=130 parent="padded-thin")

    x-img(src="images/flower.jpg" width=130 height=130)

{.caption} Цветы 

::: column(width=130)

    x-img(src="images/earth.jpg" width=130 height=130)

{.caption} планеты 

::: column(width=130)

    x-img(src="images/tree.jpg" width=130 height=130)

{.caption} деревья 

::: column(width=130)

    x-img(src="images/orange.jpg" width=130 height=130)

{.caption} Фрукты 

::: column(width=130)

    x-img(src="images/soap.jpg" width=130 height=130)

{.caption} Мыльные пузыри 

:::

{.r} И есть много других примеров: от радуги до водной ряби. Вы можете думать о чем-нибудь еще? [Продолжать](btn:next) 

---
> id: max-area
> goals: area-circle

::: column.grow

 Также оказывается, что круг - это форма с наибольшей площадью для данной окружности. Например, если у вас есть веревка длиной 100 \ m, вы можете использовать ее, чтобы заключить самое большое пространство, если вы формируете круг (а не другие формы, такие как прямоугольник или треугольник). 

 В природе такие объекты, как капли воды или пузырьки воздуха, могут _экономить энергию_ , становясь круглыми или сферическими и уменьшая площадь их поверхности. 

::: column(width=320)

    x-select.segmented
      div(data-value="0") Triangle
      div(data-value="1") Square
      div(data-value="2") Pentagon
      div(data-value="3") Circle
    svg(width=320 height=200)

{.caption} _Окружность_ = __{.m-green} 100__ , _Площадь_ = __${area}__ 

:::

---
> id: area
> goals: slider

### Площадь круга 

 Но как нам на самом деле рассчитать площадь круга? Давайте попробуем ту же технику, которую мы использовали для [нахождения площади четырехугольников](/course/polyhedra/quadrilaterals) : мы разрезаем форму на несколько разных частей, а затем перегруппируем их в другую форму, площадь которой мы уже знаем (например, прямоугольник или треугольник). 

 Единственное отличие состоит в том, что, поскольку круги изогнуты, мы должны использовать некоторые приближения: 

::: column(width=340)

    svg.circle-area.red(width=340 height=245)
      defs
        marker#area-arrow(refX=4 refY=4 markerWidth=5 markerHeight=8 orient="auto-start-reverse")
          path(d="M 1 1 L 4 4 L 1 7" stroke-width=1)
      g.labels
        line.reveal(x1=62 y1=158 x2=62 y2=212 marker-start="url(#area-arrow)" marker-end="url(#area-arrow)" when="blank-1")
        line.reveal(x1=80 y1=226 x2=268 y2=226 marker-start="url(#area-arrow)" marker-end="url(#area-arrow)" when="blank-2")
        text.reveal(x=50 y=190 when="blank-1") r
        text.reveal(x=165 y=241 when="blank-2") πr
    x-slider(steps=400)

::: column.grow

 Здесь вы можете увидеть круг, разделенный на ${toWord(n1)} клинья. Переместите ползунок, чтобы выстроить клинья в один ряд. 

{.reveal(when="slider")} Если мы увеличим количество клиньев до ${n1}{n1|6|6,30,2} эта форма начинает все больше и больше походить на [[прямоугольник | круг | квадратный]] 

{.reveal(when="blank-0")} Высота прямоугольника равна [[радиусу | длина окружности | диаметр]] круга. _{span.reveal(when="blank-1")} Ширина прямоугольника равна [[половине окружности | окружность | удвоенный радиус]] круга._ _{span.reveal(when="blank-2")} (Обратите внимание, как половина клиньев обращена вниз, а половина - вверх.)_ 

{.reveal(when="blank-2" delay=1000)} Поэтому общая площадь прямоугольника составляет примерно `A = π r^2` , 

:::

---
> id: area-1
> goals: slider

::: column(width=340)

    svg.circle-area.blue(width=340 height=245)
      g.labels
        line.reveal(x1=20 y1=156 x2=20 y2=206 marker-start="url(#area-arrow)" marker-end="url(#area-arrow)" when="blank-1")
        line.reveal(x1=34 y1=218 x2=355 y2=218 marker-start="url(#area-arrow)" marker-end="url(#area-arrow)" when="blank-2")
        text.reveal(x=10 y=185 when="blank-1") r
        text.reveal(x=165 y=236 when="blank-2") 2πr
    x-slider(steps=400)

::: column.grow

 Здесь вы можете увидеть круг, разделенный на ${toWord(n)} кольца. Как и раньше, вы можете перемещать ползунок, чтобы «раскрутить» кольца. 

{.reveal(when="slider")} Если мы увеличим количество колец до ${n2}{n2|4|2,12,1} эта форма начинает все больше и больше походить на [[треугольник | прямоугольник | трапеция]] . 

{.reveal(when="blank-0")} Высота треугольника равна [[радиусу | диаметр | Окружность]] круга. _{span.reveal(when="blank-1")} Основание треугольника равно [[окружности | двойной диаметр]] круга._ _{span.reveal(when="blank-2")} Поэтому общая площадь треугольника составляет примерно_ 

{.text-center.reveal(when="blank-2")}`A = 1/2 "base" × "height" = π r^2` , 

:::

---
> id: area-2

 Если бы мы могли использовать бесконечное количество колец или клиньев, приведенные выше приближения были бы идеальными - и они оба дают нам одинаковую формулу для площади круга: 

{.text-center.r}`A = π r^2` , [Продолжать](btn:next) 

---
> id: pi-approximations

### Расчет Пи 

 Как вы видели выше, `π = 3.1415926…` не является простым целым числом, и его десятичные цифры продолжаются вечно, без повторяющегося шаблона. Числа с этим свойством называются [__иррациональными числами__](gloss:irrational-numbers) , и это означает, что `π` не может быть выражена как простая дробь `a/b` , 

 Это также означает, что мы никогда не сможем записать _все_ цифры числа Пи - ведь их бесконечно много. Древнегреческие и китайские математики вычислили первые четыре десятичных знака числа Пи путем аппроксимации кругов с помощью правильных многоугольников. Обратите внимание, что по мере добавления новых сторон многоугольник начинает выглядеть [[все больше и больше | Меньше | точно]] как круг: 

    figure: x-img(src="images/polygons.svg" width=460 height=110)

---
> id: pi-record

::: column(width=280)

    x-img(src="images/iss.jpg" width=280 height=330 credit="NASA")

::: column.grow

 В 1665 году [Исааку Ньютону](bio:newton) удалось вычислить 15 цифр. Сегодня мы можем использовать мощные компьютеры для вычисления значения Pi с гораздо большей точностью. 

 Текущая запись составляет 31,4 триллиона цифр. Печатная книга, содержащая все эти цифры, будет иметь толщину около 400 км - это высота, на которой [Международная космическая станция](gloss:iss) вращается вокруг Земли! 

 Конечно, вам не нужно запоминать столько цифр числа Пи. На самом деле, фракция `22/7 = 3.142…` это отличное приближение. 

:::

---
> id: pi-sequence

 Один из подходов к вычислению числа Pi состоит в использовании бесконечных последовательностей чисел. Вот один пример, который был обнаружен [Готфридом Вильгельмом Лейбницем](bio:leibniz) в 1676 году: 

{.text-center}`π = 4/1 - 4/3 + 4/5 - 4/7 + 4/9 - 4/input(11) + …`

{.reveal(when="blank-0")} По мере того, как мы вычисляем все больше и больше членов этой серии, всегда следуя одной и той же схеме, результат будет становиться все ближе и ближе к Пи. 

---
> id: pi-colours
> goals: hover

::: column.grow

 Многие математики считают, что у Пи есть еще более любопытное свойство: это __нормальное число__ . Это означает, что цифры от 0 до 9 появляются совершенно случайно, как если бы природа бросала 10-гранный кубик бесконечно много раз, чтобы определить значение Pi. 

 Здесь вы можете увидеть первые 100 цифр числа Пи. Переместите некоторые ячейки, чтобы увидеть, как распределяются цифры. 

::: column(width=330)

    .pi-grid
      .pi-left
        .pi-cell 3
        .pi-operator .
      .pi-mid
        for d in '1415926535897932384626433832795028841971693993751058209749445923078164062862089986280348253421170679'.split('')
          .pi-cell= d
      .pi-right: .pi-operator …

:::

---
> id: pi-digits
> goals: search

 Если Pi нормальный, это означает, что вы можете думать о _любой_ строке цифр, и она появится где-то в ее цифрах. Здесь вы можете найти первые миллион цифр числа Пи - они содержат ваш день рождения? 

::: .box.f-red.pi-box

#### Один миллион цифр Пи 

    .pi-controls
      | Search for a string of digits:
      input(type="text" pattern="[0-9]*" maxlength=12)
      .pi-warning
    x-pi-scroll
      .first-row 3.

:::

---
> id: pi-movies

 Мы могли бы даже конвертировать целую книгу, как Гарри Поттер, в очень длинную цепочку цифр (a = 01, b = 02 и т. Д.). Если число «Пи» нормальное, эта строка появится где-то в своих цифрах - но потребуются миллионы лет, чтобы вычислить достаточно цифр, чтобы найти ее. 

 Пи легко понять, но имеет фундаментальное значение в науке и математике. Это может быть причиной того, почему Пи стал необычайно популярным в нашей культуре (по крайней мере, по сравнению с другими темами математики): 

::: column(width=220 parent="padded-thin")

    x-video(src="images/museum.mp4" poster="images/museum.jpg" width=220 height=140 audio credit="© 20th Century Fox")
    p.caption Pi is the secret combination for the tablet in “Night at the Museum 2”.

::: column(width=220)

    x-video(src="images/simpsons.mp4" poster="images/simpsons.jpg" width=220 height=140 audio credit="© Fox")
    p.caption Professor Frink (“Simpsons”) silences a room of scientists by saying that Pi equals 3.

::: column(width=220)

    x-video(src="images/star-trek.mp4" poster="images/star-trek.jpg" width=220 height=140 audio credit="© NBC")
    p.caption Spock (“Star Trek”) disables an evil computer by asking it to calculate the last digit of Pi.

:::

---
> id: pi-day

 Там даже есть _день Пи_ каждый год, который либо приходится на 14 марта, потому что `pi ≈ 3.14` или 22 июля, потому что `pi ≈ 22/7` , 

    figure: x-img(src="images/pies.jpg" width=500 height=150 credit="Evan Shelhamer, Matman from Lublin")

---

## Градусы и радианы 

> section: radians
> id: degrees

 До сих пор в геометрии мы всегда измеряли углы в [градусах](gloss:degrees) . __{.m-red} полный__ оборот на [[360]]°, __{.m-green} полукруг__ [[180]]°, а __{.m-yellow} четверть круга__ составляет [[90]]° и так далее. 

::: column(width=160)

    x-geopad(width=160 height=160): svg
      circle(x="point(150,80)" name="a0" hidden)
      circle(x="point(80,80)" name="b0")
      circle(x="c0" hidden)
      path.red.fill(x="angle(c0,b0,a0)" round size=40)
      path(x="segment(a0,b0)")
      path(x="segment(b0,c0)")

::: column(width=160)

    x-geopad(width=160 height=160): svg
      circle(x="point(150,80)" name="a1" hidden)
      circle(x="point(80,80)" name="b1")
      circle(x="c1" hidden)
      path.green.fill(x="angle(c1,b1,a1)" round size=40)
      path(x="segment(a1,b1)")
      path(x="segment(b1,c1)")

::: column(width=160)

    x-geopad(width=160 height=160): svg
      circle(x="point(150,80)" name="a2" hidden)
      circle(x="point(80,80)" name="b2")
      circle(x="c2" hidden)
      path.yellow.fill(x="angle(c2,b2,a2)" round size=40)
      path(x="segment(a2,b2)")
      path(x="segment(b2,c2)")

:::

---
> id: degrees-1

{.r} Число 360 очень удобно, потому что оно делится на множество других чисел: 2, 3, 4, 5, 6, 8, 9, 10, 12, 15 и так далее. Это означает, что многие дроби одного круга также являются целыми числами. Но вы когда-нибудь задумывались, откуда берется число 360? [Продолжать](btn:next) 

---
> id: babylon

::: column.grow

 Так получилось, что 360 градусов - это одно из древнейших понятий в математике, которое мы до сих пор используем. Они были разработаны в древнем Вавилоне более 5000 лет назад! 

 В то время одним из наиболее важных применений математики была астрономия. _Солнце_ определяет четыре сезона, о которых фермеры должны знать, когда выращивают урожай. Точно так же _луна_ определяет приливы, что было важно для рыболовов. Люди также изучали звезды, чтобы предсказывать будущее или общаться с богами. 

::: column(width=260)

    x-img(src="images/babylon.jpg" width=260 height=250 credit="Yale University")

{.caption} Вавилонская табличка для расчета `sqrt(2)`

:::

---
> id: constellations
> goals: rotate

 Астрономы заметили, что созвездия, видимые в определенное время ночью, смещались чуть-чуть каждый день - до тех пор, пока примерно через 360 дней они не повернули назад к своей исходной точке. И это могло быть причиной того, что они разделили круг на 360 градусов. 

    figure: .constellations
      .label.md Midnight on day ${day}
      .bg
      .wheel: svg(width=760 height=760 viewBox="0 0 760 760")
      .fg
    x-gesture(target=".constellations" offset="0,-120", slide="-160,0")

---
> id: constellations-1
> goals: video

 Конечно, на самом деле в одном году 365 дней (ну, точнее, 365.242199), но вавилонские математики работали с простыми солнечными часами, и это приближение было вполне адекватным. 

 Это также хорошо работало с их существующей системой счисления base-60 (так как `6 xx 60 = 360` ). Эта система является причиной того, что у нас по-прежнему есть 60 секунд в минуту и 60 минут в час - даже если большинство других единиц измеряется по [основанию 10](gloss:base-10) (например, 10 лет за десятилетие или 100 лет за столетие). 

::: column.grow

 Для многих из нас измерение углов в градусах является второй натурой: видео на 360°, скейтбордисты могут тянуть 540 с, а кто-то, изменяя свое решение, может сделать поворот на 180°. 

 Но с математической точки зрения выбор 360 совершенно произвольный. Если бы мы жили на Марсе, у круга могло бы быть 670°, а в году на Юпитере даже было 10 475 дней. 

::: column(width=280)

    x-video(src="images/skateboard.mp4" poster="images/skateboard.jpg" width=280 height=200 credit="© RIDE Channel, from YouTube")

{.caption} 540 McFlip, поворот на 540° 

:::

---
> id: radians

### Радиан 

 Вместо того, чтобы делить круг на некоторое количество сегментов (например, 360 градусов), математики часто предпочитают измерять углы, используя [окружность](gloss:circle-circumference) [__единичного круга__](gloss:unit-circle) (круг с радиусом 1). 

::: column(width=280)

    x-geopad(width=280 height=280): svg
      circle(x="point(140,140)" name="c")
      path.thin(x="circle(c,100)" name="circ")
      circle.move.blue.pulsate(cx=240 cy=140 name="a" project="circ")
      circle.move.green(cx=240 cy=140.4 name="b" project="circ")
      path.fill.green(x="angle(b,c,a)" label="${round(ang.deg)}°" name="ang" round)
      path.red.thick(x="arc(c,b,ang.rad)" label="${rad(ang.rad)}π")
      path.thin(x="segment(c,a)")
      path.thin(x="segment(c,b)")

::: column.grow

 _{span.var-action} полный круг_ имеет окружность _{x-equation.small(solution="2 π" keys="+ × π" numeric)}_ , 

{.reveal(when="eqn-0")} Для _{span.var-action} поворот на полукруга_ , соответствующее расстояние по окружности _{x-equation.small(solution="π" keys="+ × π" numeric)}_ , 

{.reveal(when="eqn-1")} Для _{span.var-action} вращение_ на _четверть круга_ , расстояние по окружности _{x-equation.small(solution="π/2" keys="+ × π frac" numeric)}_ , 

{.reveal(when="eqn-2")} И так далее: этот способ измерения углов называется [__радианами__](gloss:radians) (вы можете помнить это как «единицы радиуса»). 

:::

---
> id: radians-conversion

 Каждый угол в градусах имеет эквивалентный размер в радианах. Преобразование между ними очень просто - точно так же, как вы можете конвертировать между другими единицами измерения, например, метрами и километрами или градусами Цельсия и Фаренгейта: 

{.text-center} __{.m-red} 360°__ _{span.space} знак равно_ __{.m-green} 2 _π_ рад__ 

::: column(width=180 parent="padded-thin")

{.text-center} _{span.rotate.left}`=>`_  
__{.m-red} 1°__ _{span.space} знак равно_ [[`pi/180`|`180pi`|`360/pi`]] __{.m-green} радиан__ 

::: column(width=180)

{.text-center} _{span.rotate.right}`=>`_  
__{.m-green} 1 рад__ _{span.space} знак равно_ [[`180/pi`|`180-pi`|`2pi-360`]] __{.m-red}°__ 

:::

---
> id: radians-table

 Вы можете записать значение в радианах либо как кратное _π_ , либо как одно десятичное число. Можете ли вы заполнить эту таблицу эквивалентных угловых размеров в градусах и радианах? 

 | __{.m-red} градусы__ | 0 | 60 | _{x-equation.small(solution="360/π" keys="π frac" numeric)}_ | 180 | _{x-equation.small(solution="270" keys="π frac" numeric)}_ | | __{.m-green} радианы__ | 0 | _{x-equation.small(solution="π/3" keys="π frac" numeric)}_ | 2 | _{x-equation.small(solution="π" keys="π frac" numeric)}_ | `3/2 pi` | {.table-small.grid}

---
> id: radians-distance

### Пройденное расстояние 

 Вы можете думать о радианах как о «пройденном расстоянии» по окружности единичного круга. Это особенно полезно при работе с объектами, которые движутся по круговой траектории. 

::: column.grow

 Например, [Международная космическая станция](gloss:iss) вращается вокруг Земли один раз каждые 1,5 часа. Это означает, что его __скорость вращения__ [[`(2 pi)/1.5`|`1.5/(2 pi)`|`1.5 * pi`]] радианы в час. 

{.reveal(when="blank-0")} В [единичном круге](gloss:unit-circle) скорость вращения равна _фактической_ скорости, потому что длина окружности такая же, как один полный оборот в радианах (оба `2pi` ). 

{.reveal(when="blank-0" delay=1000)} Радиус орбиты МКС составляет 6800 \ км, что означает, что _фактическая_ скорость МКС должна быть [[`(2 pi)/1.5 xx 6800`|`(2 pi)/1.5 ÷ 6800`|`6800/(2 * pi)`]] _{span.reveal(when="blank-1")} = 28483 км в час._ 

::: column(width=300)

    x-geopad.r(width=300 height=300)
      .earth
      svg.r
        circle(x="point(150,150)" name="c")
        circle(x="point(280,150)" name="a")
        circle(x="a.rotate(p*2*pi,c)" name="b" hidden)
        path.red(x="arc(c,a,p*2*pi)")
        path.fill(x="angle(a,c,b)" label="${round(2*p,1)}π" round)
        path.red(x="segment(c,a)")
        path.red(x="segment(c,b)")
      .var.iss(style="transform: translate(${a.rotate(p*2*pi,c).x}px,${a.rotate(p*2*pi,c).y}px) rotate(${(p+0.25)*2*pi}rad)")
      .time.var ${round(p*1.5,1)}h
      x-play-btn

:::

---
> id: radians-distance-1

 Видите ли вы, что в этом примере радианы являются гораздо более удобной единицей, чем градусы? Как только мы узнаем скорость вращения, нам просто нужно умножить на радиус, чтобы получить фактическую скорость. 

 Вот еще один пример: у вашей машины есть колеса с радиусом 0,25 \ м. Если вы едете со скоростью 20 м / с, колеса вашего автомобиля вращаются со [[`20/0.25 =
80`|`20 xx 0.25 = 5`|`0.25/50 = 0.0125`]] радианы в секунду _{span.reveal(when="blank-0")} (или `80/(2pi) = 13` оборотов в секунду)._ 

---
> id: radians-trig

### тригонометрия 

 Для большинства простых геометрических задач градусы и радианы полностью взаимозаменяемы - вы можете выбрать, какой из них вы предпочитаете, или вопрос может сказать вам, в какой единице дать ответ. Однако, как только вы изучите более сложную [тригонометрию](gloss:trigonometry) или [исчисление](gloss:calculus) , получается что радианы намного удобнее, чем градусы. 

::: column.grow

 Большинство калькуляторов имеют [специальную кнопку](->.button.mode) для переключения между градусами и радианами. Тригонометрические функции, такие как [__sin__](gloss:sin) , [__cos__](gloss:cos) и __tan,__ принимают углы в качестве входных данных, а их обратные функции __arcsin__ , __arccos__ и __arctan__ возвращают углы в качестве выходных данных. Текущая настройка калькулятора определяет, какие единицы измерения используются для этих углов. 

 Попробуйте использовать этот калькулятор, чтобы рассчитать, что 

{.text-center} грех (30°) = [[0,5]] _{span.eqn-gap}_ cos (1°) = [[0,999]]  
грех (30 рад) = [[-0,988]] _{span.eqn-gap}_ cos (1 рад) = [[0,54]] 

::: column(width=300)

    .calculator
      .display
        span
        .setting DEG
      .button.num 7
      .button.num 8
      .button.num 9
      .button.wide sin
      .button.num 4
      .button.num 5
      .button.num 6
      .button.wide cos
      .button.num 1
      .button.num 2
      .button.num 3
      .button.wide tan
      .button.num 0
      .button .
      .button C
      .button.wide.mode mode

:::

---
> id: small-angle

 Использование радианов имеет одно особенно интересное преимущество при использовании функции синуса. Если `θ` очень маленький угол (менее 20° или 0,3 рад), то `sin(θ) ≈ θ` , Например, 

{.text-center} грех ( ${x}{x|0.1|0,0.5,0.05} ) `≈`${sin(x)} ... 

{.reveal(when="var-0")} Это называется __приближением малых углов__ , и оно может значительно упростить некоторые уравнения, содержащие тригонометрические функции. Вы узнаете намного больше об этом в будущем. 

---

## Касательные, аккорды и дуги 

> section: tangets-chords-arcs
> id: circle-parts

 В предыдущих разделах вы узнали имена, данные нескольким различным частям круга - например, центр, радиус, диаметр и окружность. Однако есть много геометрических элементов, связанных с кругом, которые нам понадобятся для решения более сложных задач: 

::: column(width=300)

    x-geopad.sticky(width=300 height=300): svg
      circle(x="point(150,150)" name="x")
    
      path.teal.fill.reveal(x="sector(x,d1,pi/2.5)" target="sector" when="next-3" label="Sector" label-class="white")
      path.purple.fill.reveal(x="arc(x,b1,pi/2.5)" target="segment" when="next-4" label="Segment")
    
      path.black(x="circle(x,100)" name="c")
    
      circle.red(x="c.at(0.5)" name="a1" target="secant")
      circle.red(x="c.at(0.7)" name="a2" target="secant")
      path.red.thick(x="line(a1,a2)" label="Secant" target="secant")
    
      circle.green.reveal(x="c.at(0.8)" name="b1" target="chord" when="next-0" animation="pop")
      circle.green.reveal(x="c.at(0)" name="b2" target="chord" when="next-0" animation="pop")
      path.green.thick.reveal(x="segment(b1,b2)" label="Chord" target="chord" when="next-0" animation="draw")
    
      circle.blue.reveal(x="c.at(0.1)" name="c1" target="tangent" when="next-1" animation="pop")
      path.blue.thick.reveal(x="c.tangentAt(0.1)" label="Tangent" target="tangent" when="next-1" animation="draw")
    
      circle.yellow.reveal(x="c.at(0.2)" name="d1" target="arc" when="next-2" animation="pop")
      circle.yellow.reveal(x="c.at(0.4)" name="d2" target="arc" when="next-2" animation="pop")
      path.yellow.thick.reveal(x="arc(x,d1,pi/2.5)" label="Arc" target="arc" when="next-2" animation="draw")

::: column.grow(parent="right")

 * {.r} [{.red} секущая](pill:secant) - это линия, которая пересекает круг в двух точках. [Продолжить](btn:next) * {.r.reveal(when="next-0")} [{.green} хорда](pill:chord) - это отрезок, конечные точки которого лежат на окружности круга. [Продолжить](btn:next) * {.r.reveal(when="next-1")} [{.blue} Касательная](pill:tangent) - это линия, которая касается круга ровно в одной точке. Это называется __точкой касания__ . [Продолжить](btn:next) * {.r.reveal(when="next-2")} [{.yellow} дуга](pill:arc) - это отрезок окружности круга. [Продолжить](btn:next) * {.r.reveal(when="next-3")} [{.teal} сектор](pill:sector) является частью внутренней части круга, ограниченной _дугой_ и _двумя радиусами_ . [Продолжить](btn:next) * {.r.reveal(when="next-4")} Наконец, [{.purple} сегмент](pill:segment) является частью внутренней части круга, ограниченного _дугой_ и _хордой_ . [Продолжать](btn:next) 

:::

---
> id: circle-parts-1

 В этом разделе мы рассмотрим взаимосвязь между всеми этими элементами и докажем теоремы об их свойствах. Пока не беспокойтесь о запоминании всех определений - вы всегда можете использовать [глоссарий](->.footer-link[data-modal=glossarym]) . 

---

### Касательные 

{.todo} СКОРО БУДЕТ! 

    // https://www.mathopenref.com/tangentline.html
    // https://www.mathopenref.com/consttangents.html
    // https://www.mathopenref.com/consttangent.html
    
    // __[CC] Construct a tangent line from a point outside a given circle to the circle.__
    // 
    // Point of Tangency: The point where a tangent line touches the circle.
    // 
    // The tangent line and the radius drawn to the point of tangency have a unique
    // relationship. Let’s investigate it here.
    // 
    // _Tangent to a Circle Theorem_: A line is tangent to a circle if and only if the
    // line is perpendicular to the radius drawn to the point of tangency.
    // 
    // To prove this theorem, the easiest way to do so is indirectly (proof by
    // contradiction). Also, notice that this theorem uses the words “if and only if,”
    // making it a biconditional statement. Therefore, the converse of this theorem is
    // also true. Now let’s look at two tangent segments, drawn from the same external
    // point. If we were to measure these two segments, we would find that they are equal.
    // 
    // _Two Tangents Theorem_: If two tangent segments are drawn from the same external
    // point, then the segments are equal.
    //
    // Tangents are actually a much more universal concept,
    // Tangent Circles: Two or more circles that intersect at one point.
    // Two circles can be tangent to each other in two different ways, either
    // internally tangent or externally tangent.

---

### Аккорды 

{.todo} СКОРО БУДЕТ! 

    // A chord is a line segment whose endpoints are on a circle. A diameter is the
    // longest chord in a circle. There are several theorems that explore the
    // properties of chords.
    // 
    // Chord Theorem #1: In the same circle or congruent circles, minor arcs are
    // congruent if and only if their corresponding chords are congruent.
    // 
    // Notice the “if and only if” in the middle of the theorem. This means that Chord
    // Theorem #1 is a biconditional statement. Taking this theorem one step further,
    // any time two central angles are congruent, the chords and arcs from the
    // endpoints of the sides of the central angles are also congruent. In both of
    // these pictures, BE≅CD and BEˆ≅CDˆ. In the second picture, we have △BAE≅△CAD
    // because the central angles are congruent and BA≅AC≅AD≅AE because they are all
    // radii (SAS). By CPCTC, BE≅CD.
    // 
    // Investigation: Perpendicular Bisector of a Chord
    // 1. Draw a circle. Label the center A. 
    // 2. Draw a chord in ⨀A. Label it BC.
    // 3. Find the midpoint of BC by using a ruler. Label it D. 
    // 4. Connect A and D to form a diameter. How does AD relate to the chord, BC? 
    // 
    // Chord Theorem #2: The perpendicular bisector of a chord is also a diameter.
    // In the picture to the left, AD⊥BC and BD≅DC. From this theorem, we also notice
    // that AD also bisects the corresponding arc at E, so BEˆ≅ECˆ.
    // 
    // Chord Theorem #3: If a diameter is perpendicular to a chord, then the diameter
    // bisects the chord and its corresponding arc.
    // 
    // Investigation: Properties of Congruent Chords
    // 1. Draw a circle with a radius of 2 inches and two chords that are both 3
    //    inches. Label as in the picture to the right. This diagram is drawn to scale. 
    // 2. From the center, draw the perpendicular segment to AB and CD.
    // 3. Erase the arc marks and lines beyond the points of intersection, leaving FE
    //    and E. Find the measure of these segments. What do you notice? 
    // 
    // Chord Theorem #4: In the same circle or congruent circles, two chords are
    // congruent if and only if they are equidistant from the center.
    // 
    // Recall that two lines are equidistant from the same point if and only if the
    // shortest distance from the point to the line is congruent. The shortest distance
    // from any point to a line is the perpendicular line between them. In this
    // theorem, the fact that FE=EG means that AB and CD are equidistant to the center
    // and AB≅CD.
    
    // Concentric Circles: Two or more circles that have the same center, but different radii.
    // Congruent Circles: Two or more circles with the same radius, but different centers.

---
> id: earth-arc

### Дуги и сектора 

::: column.grow

 Большинство ученых древней Греции согласились с тем, что Земля - это сфера. Было много доказательств: от кораблей, скрывающихся за горизонтом в море, до кругового движения звезд ночью. 

 К сожалению, никто точно не знал, _насколько велика_ Земля - примерно до 200 г. до н.э., когда математик [Эратосфен](bio:eratosthenes) нашел оригинальный способ измерения радиуса Земли, используя базовую геометрию. Все, что нам нужно, это немного больше знаний о дугах и секторах круга. 

::: column(width=280)

    x-solid(size=280 rotate="0.5")

:::

---
> id: arcs

::: column(width=280)

    x-geopad.sticky(width=280 height=280): svg
      circle(x="point(140,140)" name="c")
      path(x="circle(c,100)" name="circ")
      circle.move(cx=240 cy=140 name="a" project="circ" label="A")
      circle.move(cx=85 cy=60 name="b" project="circ" label="B")
    
      path.yellow.fill(x="sector(c,b,angle(b,c,a).rad).minor" label="Sector" target="sector" label-class="white")
      path.red.thick(x="arc(c,b,angle(b,c,a).rad).minor" label="Arc" target="arc")
      path.purple.thick.transparent(x="arc(c,a,2*pi-angle(b,c,a).rad).major" target="major")

::: column.grow

 Как вы можете видеть на диаграмме, [{.red} дуга](pill:arc) является частью [[окружности | диаметр | касательная]] окружности, а [{.yellow} сектор](pill:sector) является частью [[интерьера | радиус | периметр]] круга. 

::: .reveal(when="blank-0 blank-1")

 Дуга между двумя точками _A_ и _B_ часто записывается как `arc(AB)` , Это определение немного двусмысленно: есть [{.purple} вторая дуга,](pill:major) которая соединяет _А_ и _В,_ но идет по кругу. 

 Меньшая из двух дуг называется __малой дугой__ , а большая - __главной дугой__ . Если точки _A_ и _B_ точно противоположны друг другу, обе дуги имеют одинаковую длину и являются [[полукругами | диаметры | окружности]] 

:::

:::

---
> id: arcs-1

::: column.grow

 Чтобы найти длину дуги или площадь сектора, нам нужно знать о соответствующем угле в центре круга: это называется [{.blue} центральный угол](pill:angle) . 

 Обратите внимание, что дуга, сектор и угол занимают _одинаковую пропорцию_ полного круга. Например, если [{.blue} центральный угол](pill:angle) _{span.var-action} 90°_ , занимает [[одну четверть | одна половина | одна треть]] [{.teal} полный круг](pill:fangle) 

::: .reveal(when="blank-0")

 Это означает, что [{.red} длина дуги](pill:arc) также `1/4` из [{.purple} всю окружность](pill:circ) круга, а [{.yellow} Площадь сектора](pill:sector) `1/4` из [{.orange} вся площадь](pill:area) круга. 

 Мы можем выразить это отношение в уравнении: 

{.text-center}`"arc length" / "circumference" = blank("sector area","circle radius","arc area") / "circle area" = "central angle" / blank("360°","180°","90°")`

:::

::: column(width=280)

    x-geopad.sticky(width=280 height=280): svg
      circle(x="point(140,140)" name="c")
      path(x="circle(c,100)" name="circ")
      circle.move(cx=240 cy=140 name="a" project="circ")
      circle.move(cx=85 cy=60 name="b" project="circ")
    
      path.yellow.fill(x="sector(c,b,angle(b,c,a).rad)" label="Sector" target="sector" label-class="white")
      path.red.thick(x="arc(c,b,angle(b,c,a).rad)" label="Arc" target="arc")
      path.fill.blue(x="angle(b,c,a)" target="angle")
    
      path.fill.orange.transparent(x="circ" target="area")
      path.thick.purple.transparent(x="circ" target="circ")
      path.teal.fill.transparent(x="circle(c,32)" target="fangle")

:::

---
> id: arcs-2

 Теперь мы можем переставить эти уравнения, чтобы найти любую интересующую нас переменную. Например, 

::: column(width=320 parent="padded-thin")

 | [{.red} длина дуги](pill) | = | `"circumference" × c/360` | | | = | `2 π r × c/360` | {.eqn-system}

::: column(width=320)

 | [{.yellow} площадь сектора](pill) | = | `"circle area" × c/360` | | | = | `π r^2 × c/360` | {.eqn-system}

:::

 где _r_ - радиус круга, а _c_ - размер центрального угла. 

    // What the formulae are doing is taking the area of the whole circle, and
    // then taking a fraction of that depending on what fraction of the circle
    // the sector fills.
    
    // The length of an arc is the distance along the curved line of the
    // circumference of the circle. It is slightly longer than the straight
    // line connecting the same two points (the chord).

---
> id: arcs-rad

 Если центральный угол измеряется в [радианах,](gloss:radians) а не в [градусах](gloss:degrees) , мы можем использовать те же уравнения, но заменить 360° на [[`2 π`|`1/2 π`|`π`]] : 

::: .reveal(when="blank-0")

::: column(width=320 parent="padded-thin")

 | [{.red} длина дуги](pill) | = | `2 π r × c/(2π)` | | | = | `r × c` | {.eqn-system}

::: column(width=320)

 | [{.yellow} площадь сектора](pill) | = | `π r^2 × c/(2π)` | | | = | `1/2 r^2 c` | {.eqn-system}

:::

 Обратите внимание на то, как уравнения становятся намного проще, и _π_ исчезает везде. Это потому, что, как вы помните, [определение радианов](/course/circles/radians#radians) - это в основном длина дуги в круге с радиусом 1. 

 Теперь давайте посмотрим, как мы можем использовать дуги и сектора для расчета окружности Земли. [Продолжать](btn:next) 

:::

---
> id: eratosthenes

 В древнем Египте город _Свенет_ располагался вдоль реки Нил. Свенет был знаменит колодцем с любопытным свойством: каждый год был один момент, когда солнечный свет достигал самого дна колодца - в полдень 21 июня, в день _летнего солнцестояния_ . В это точное время было освещено дно колодца, но не его стороны, что означало, что Солнце стояло прямо над колодцем. 

::: column(width=300)

    x-img(src="images/egypt-map.jpg" width=300 height=300 lightbox credit="© Google Maps")

{.caption} Древние египтяне измеряли большие расстояния, подсчитывая количество шагов, которые нужно было пройти. 

::: column(width=300)

    x-img(src="images/well.jpg" width=300 height=300 lightbox)

{.caption} Некоторые источники сообщают, что «Колодец Эратосфена» находился на _острове Элефантин_ на реке Нил. 

:::

 Математик [Эратосфен](bio:eratosthenes) жил в _Александрии_ , примерно в 800 км к северу от Свенета, где он был директором Большой библиотеки. В центре города Александрия стоял обелиск, высокий, узкий памятник с вершиной в форме пирамиды. 

 Эратосфен заметил, что в полдень в день летнего солнцестояния обелиск отбросил тень - это означает, что солнце _не было_ прямо над ним. Он сделал вывод, что это из-за искривления Земли, и понял, что его можно использовать для расчета окружности нашей планеты. 

---
> id: eratosthenes-1

::: column.grow

{.r} Здесь вы можете увидеть колодец в Свене, а также обелиск в Александрии. Солнечные лучи падают прямо в колодец, но ударяют обелиск под углом и отбрасывают тень. [Продолжать](btn:next) 

::: .reveal(when="next-0")

 Эратосфен измерил, что [{.teal} угол](pill:angle1) тени составлял 7,2°. Это так же, как [{.purple} центральный угол](pill:angle2) [{.red} дуга](pill:arc) из Александрии в Свенет, потому что они [[чередуются | вертикальный | соответствующие]] углы. 

:::

::: .reveal(when="blank-0")

 Теперь мы можем использовать уравнение для длины дуги, которое мы вывели выше: 

{.text-center}`pill("arc length","red","arc") / pill("circumference","blue","circ") = (input(7.2)"°") / "360°"`

:::

::: .reveal(when="blank-1")

 Если мы изменим это, мы обнаружим, что окружность Земли 

{.text-center}`pill("circumference","blue","circ") = "360°" / "7.2°" × pill("800 km","red","arc") = input(40000) "km"`

:::

::: .reveal(when="blank-2")

 Наконец, мы знаем, что окружность круга `C = 2 pi r` , поэтому радиус Земли 

{.text-center}`r_"Earth" = (40000 "km") / (2 pi) ≈ 6400 "km"` , 

:::

::: column(width=300)

    x-geopad.sticky(width=300 height=400)
      img.sunrays(src="images/sunlight.png" width=300 height=400)
      svg.r
        defs: radialGradient#grad1(cx=200 cy=200 r=200 gradientUnits="userSpaceOnUse")
          stop(offset=0 stop-color="#63a3ff")
          stop(offset=1 stop-color="#0f82f2")
    
        circle(x="point(150,250)" name="c" hidden)
        circle(x="point(150,120)" name="a" hidden)
        circle.move.pulsate(cx=80 cy=140 name="b" project="arc(c,point(64,155),1.47)")
        circle(x="c.add(b.subtract(c).scale(1.465))" name="d" hidden)
    
        path.shadow(x="triangle(c,d,point(d.x,c.y))")
        path.earth(d="M153,120,152,150h-4l-.95-30a130,130,0,1,0,5.9,0Z" fill="url(#grad1)")
        path.earth-cover.fill(x="circle(c,130)")
    
        path.red.thick.reveal(when="next-0" animation="draw" x="arc(c,b,angle(b,c,a).rad).minor" target="arc")
        path.fill.teal.reveal(when="next-0" x="angle(c,d,point(d.x,c.y)).sup" target="angle1")
        path.fill.purple.reveal(when="next-0" x="angle(b,c,a).sup" name="ang" target="angle2")
        path.thin.white.reveal(when="next-0" animation="draw" x="segment(c,b)")
        path.blue.transparent(x="circle(c,130)" target="circ")
    
        image.obelisk.var(xlink:href="images/obelisk.svg" height=60 width=8 style="transform: translate(${b.x-4}px, ${b.y-60}px) rotate(-${angle(b,c,a).rad}rad)")

:::

---
> id: eratosthenes-2

 Измерение Эратосфена было одним из самых важных экспериментов в древности. Его оценка размера Земли была на удивление точной, особенно если учесть, что он имел доступ только к самым базовым измерительным инструментам. 

::: column(width=280)

    x-img(src="images/obelisk.jpg" width=280 height=450 lightbox)

::: column.grow

 Конечно, может быть трудно перевести его первоначальные результаты в современные единицы, например, в километры. В древней Греции расстояние измерялось в _стадиях_ (примерно 160 м), но универсального стандарта не было. У каждой области была немного другая версия, и мы не знаем, какой из них использовал Эратосфен. 

 В последующие века ученые пытались использовать другие методы для расчета радиуса Земли - иногда с совершенно разными и неверными результатами. 

 Это было одно из этих неверных измерений, которое побудило Христофора Колумба плыть на запад из Португалии. Он предположил, что Земля намного меньше, чем есть на самом деле, и надеялся достичь Индии. Фактически, он прибыл на другой континент между Америками. 

:::

---

### Сегменты 

{.todo} СКОРО БУДЕТ! 

    // The last part of a circle that we can find the area of is called a segment, not
    // to be confused with a line segment. A segment of a circle is the area of a
    // circle that is bounded by a chord and the arc with the same endpoints as the
    // chord. The area of a segment is Asegment=Asector−A△ABC

---

## Теорема о круге 

> section: circle-theorems
> sectionStatus: dev

 https://www.mathsisfun.com/geometry/circle-theorems.html https://mathsmadeeasy.co.uk/gcse-maths-revision/circle-theorems-gcse-revision-and-worksheets/ http: // amsi .org.au / teacher_modules / Circle_Geometry.html 

 __[CC] Определите и опишите отношения между вписанными углами, радиусами и аккордами. Включите связь между центральным, вписанным и ограниченным углами; вписанные углы по диаметру являются прямыми углами; радиус окружности перпендикулярен касательной, где радиус пересекает окружность.__ 

 Вписанный угол - это угол, вершина которого - это круг, а его стороны содержат аккорды. Перехваченная дуга - это дуга, которая находится внутри вписанного угла и чьи конечные точки находятся на углу. Вершина вписанного угла может находиться в любом месте круга, если его стороны пересекают круг, образуя перехваченную дугу. 

 __Теорема__ о вписанном угле Мера вписанного угла равна половине меры перехваченной дуги. Чтобы доказать теорему о вписанных углах, вам нужно разделить ее на три случая, например, на три разных угла, взятых из исследования. 

 __Теорема о конгруэнтном вписанном угле__ Вписанные углы, пересекающие одну и ту же дугу, конгруэнтны. 

 __Теорема__ о полукруге с __вписанным углом__ Угол, который пересекает полукруг, является прямым углом. 

 В теореме о полукруге с вписанным углом мы также можем сказать, что угол вписан в полукруг. Каждый раз, когда в круг вписывается прямой угол, конечные точки угла являются конечными точками диаметра. Следовательно, верно и обратное к теореме о полукруге на вписанном угле. 

 Когда угол находится на окружности, вершина находится на окружности круга. Один тип угла на окружности - это угол, образованный касательной и хордой. 

 __Теорема об аккорде / касательном__ угле Мера угла, образованного хордой и касательной, которая пересекается по окружности, является половиной меры перехваченной дуги. 

 Из теоремы о хорде / касательном угле мы теперь знаем, что есть два типа углов, которые являются половиной меры перехваченной дуги; вписанный угол и угол, образованный хордой и касательной. Следовательно, любой угол с его вершиной на окружности будет вдвое меньше меры перехваченной дуги. 

 Угол рассматривается внутри круга, когда вершина находится где-то внутри круга, но не в центре. Все углы внутри круга образованы двумя пересекающимися хордами. 

 __Теорема__ об угле пересечения хорд Мера угла, образованного двумя хордами, которые пересекаются внутри круга, является средней величиной меры перехваченных дуг. 

 Угол считается за пределами круга, если вершина угла находится за пределами круга, а стороны являются касательными или секущими. Есть три типа углов, которые находятся вне круга: угол, образованный двумя касательными, угол, образованный касательной и секущей, и угол, образованный двумя секционными. Точно так же, как угол внутри или на окружности, угол вне окружности имеет особую формулу, включающую перехваченные дуги. 

 __Теорема__ о внешнем угле Мера угла, образованного двумя секущими, двумя касательными или секущей и касательной, нарисованной из точки вне круга, равна половине разницы мер перехваченных дуг. 

 Когда два аккорда пересекаются внутри круга, два треугольника, которые они создают, похожи, и стороны каждого треугольника пропорциональны друг другу. Если мы удалим AD и BC, отношения между AE, EC, DE и EB останутся прежними. 

 __Теорема о пересекающихся аккордах__ Если два аккорда пересекаются внутри круга так, что один делится на отрезки длины a и b, а другой - на отрезки длины c и d, тогда ab = cd. Другими словами, произведение сегментов одного пояса равно произведению сегментов второго пояса. 

 Помимо формирования угла вне круга, круг может делить секущие на сегменты, которые пропорциональны друг другу. 

 Если мы рисуем пересекающиеся аккорды, у нас будет два одинаковых треугольника. 

 Из вписанных углов и рефлексивного свойства (∠R≅∠R), △ PRS∼ △ TRQ. Поскольку два треугольника похожи, мы можем установить пропорцию между соответствующими сторонами. Затем кросс-умножить. ас + д = Ca + b⇒a (а + б) = с (с + d) 

 __Теорема о__ двух секущих __сегментах__ Если два секущих нарисованы из общей точки вне круга и сегменты помечены, как указано выше, то a (a + b) = c (c + d). Другими словами, произведение внешнего сегмента и всего одного секущего равно произведению внешнего сегмента и всего другого секущего. 

 Если касательная и секущая встречаются в общей точке за пределами круга, созданные сегменты имеют отношение, аналогичное отношению двух секущих лучей. Напомним, что произведение внешней части секущей и целой равняется таковой другой секущей. Если один из этих сегментов является касательной, он все равно будет произведением внешней части и целого. Однако для касательной линии внешняя часть и целое равны. 

 __Теорема о сегменте касательного сегмента__ Если касательная и секущая нарисованы из общей точки вне круга (и сегменты помечены как рисунок слева), то a2 = b (b + c). Это означает, что произведение наружного сегмента на секущий и целое равно квадрату касательного сегмента. 

---

### Теорема Фалеса 

 Доказательство с использованием равнобедренных треугольников 

 Объединяет всю евклидову геометрию 

{.todo} ДЕЛАТЬ 

---

## Циклические Полигоны 

> sectionStatus: dev
> section: cyclic-polygons

 __[CC] Постройте равносторонний треугольник, квадрат и правильный шестиугольник, вписанный в круг.__ 

 Вписанный многоугольник - это многоугольник, в котором каждая вершина находится на окружности. Обратите внимание, что не каждый четырехугольник или многоугольник может быть вписан в круг. Вписанные четырехугольники также называют циклическими четырехугольниками. Для этих типов четырехугольников они должны иметь одно специальное свойство. Мы будем исследовать это здесь. 

 Это исследование показывает, что противоположные углы в вписанном четырехугольнике являются дополнительными. Разрезав четырехугольник пополам по диагонали, мы смогли показать, что два других угла (которые мы не прорезали) образовали линейную пару при сопоставлении. 

 Четырехугольная теорема с надписью: Четырехугольник вписан в окружность тогда и только тогда, когда противоположные углы являются дополнительными. 

 https://www.youtube.com/watch?v=bJOuzqu3MUQ 

---

## Сферы, конусы и цилиндры 

> section: spheres-cones-cylinders
> id: solids

 В предыдущих разделах мы изучали свойства окружностей на плоской поверхности. Но наш мир на самом деле трехмерный, поэтому давайте взглянем на некоторые трехмерные тела, основанные на кругах: 

::: column(width=220 parent="padded-thin")

    x-solid(size=220)

{.text-center} [__Цилиндр__](gloss:cylinder) состоит из двух параллельных параллельных окружностей, соединенных изогнутой поверхностью. 

::: column(width=220)

    x-solid(size=220)

{.text-center} [__Конус__](gloss:cone) имеет круглое основание, соединенное с одной точкой (называемой вершиной). 

::: column(width=220)

    x-solid(size=220 static)

{.text-center} Каждая точка на поверхности [__сферы__](gloss:sphere) имеет одинаковое расстояние от ее центра. 

:::

 Обратите внимание, что определение сферы почти совпадает с определением [[круга | радиус | куб]] - кроме трех измерений! 

---
> id: gasometer

### Цилиндры 

::: column.grow

 Здесь вы можете увидеть цилиндрический _газометр_ в Оберхаузене, Германия. Он использовался для хранения природного газа, который использовался в качестве топлива на близлежащих заводах и электростанциях. Газометр имеет высоту 120 метров, а его основание и потолок представляют собой два больших круга радиусом 35 метров. Есть два важных вопроса, на которые инженеры могут захотеть ответить: 

 * Сколько природного газа можно хранить? Это [[объем | площадь | диаметр]] цилиндра. * {.reveal(when="blank-0")} Сколько стали нужно, чтобы построить газометр? Это (приблизительно) [[площадь поверхности | длина окружности | диагональ]] цилиндра. 

{.reveal(when="blank-0 blank-1")} Попробуем найти формулы для обоих этих результатов! 

::: column(width=300)

    x-img(src="images/gasometer.jpg" width=300 height=400 lightbox)

{.caption} Газометр Оберхаузен 

:::

---
> id: cylinder-prism

#### Объем цилиндра 

 Верх и низ цилиндра представляют собой два конгруэнтных круга, называемых __основаниями__ . __{.m-blue} высота _h___ цилиндра представляет собой перпендикулярное расстояние между этими основаниями, и __{.m-red} радиус _r___ цилиндра - это просто радиус круговых оснований. 

 Мы можем приблизить цилиндр с помощью ${n}{n|5|3,20,1} [__призма__](gloss:prism) . По мере увеличения количества сторон призма начинает все больше походить на цилиндр: 

::: column(width=240)

    x-solid(size=240)

::: column(width=240)

    x-solid(size=240)

:::

---
> id: cylinder-volume

 Хотя цилиндр технически не является призмой, он обладает многими свойствами. В обоих случаях мы можем найти объем, умножив площадь их __{.m-red} база__ с их __{.m-blue} высота__ Это означает, что цилиндр с радиусом _{.b.m-red} г_ и высота _{.b.m-blue} ч_ имеет объем 

{.text-center}`V =` _{x-equation(solution="π r^2 h" keys="+ − × ÷ π frac sup brackets" short-var hints="cylinder-volume-hint1 cylinder-volume-hint2")}_ 

{.reveal(when="eqn-0")} Помните, что радиус и высота должны использовать одинаковые единицы. Например, если _r_ и _h_ оба в см, то объем будет в [[`"cm"^3`|`"cm"^2`| см]] 

---
> id: oblique-cylinder
> goals: slide

::: column.grow

 В приведенных выше примерах два основания цилиндра всегда были _непосредственно друг над другом_ : это называется __правым цилиндром__ . Если основания не находятся прямо друг над другом, у нас есть __наклонный цилиндр__ . Основания все еще параллельны, но стороны, кажется, «наклоняются» под углом, не равным 90°. 

    x-solid(size="300,200" static)
    x-gesture(target="#oblique-cylinder x-solid" slide="40,0")

::: column(width=300)

    x-img(src="images/pisa.jpg" width=300 height=360 lightbox)

{.caption} _Пизанская башня_ в Италии - не совсем косой цилиндр. 

:::

---
> id: cavalieri
> goals: slide

 Объем наклонного цилиндра оказывается точно таким же, как у правого цилиндра с таким же радиусом и высотой. Это связано с [__принципом Кавальери__](gloss:cavalieri) , названным в честь итальянского математика [Бонавентуры Кавальери](bio:cavalieri) : если два тела имеют одинаковую площадь поперечного сечения на каждой высоте, то они будут иметь одинаковый объем. 

 Представьте себе нарезку цилиндра на множество тонких дисков. Затем мы можем сдвинуть эти диски в горизонтальное положение, чтобы получить наклонный цилиндр. Объем отдельных дисков не изменяется, так как вы делаете его наклонным, поэтому общий объем также остается постоянным: 

::: column(width=240)

    x-solid(size=280 style="margin: -20px")

::: column(width=240)

    x-solid.slide-me(size=280 static style="margin: -20px")
    x-gesture(target=".slide-me" slide="60,0")

:::

    // TODO You must always use the _perpendicular_ height. This is
    // the vertical line to left in the figure above.
    
    // TODO Volume of horizontal cylinder segments
    // https://www.mathopenref.com/cylindervolpartial.html

---
> id: cylinder-surface

#### Площадь поверхности цилиндра 

::: column.grow

 Чтобы найти площадь поверхности цилиндра, нам нужно «развернуть» его в плоскую [сетку](gloss:net) . Вы можете попробовать это сами, например, сняв этикетку с банки с едой. 

 Есть два [[круга | сферы | квадраты]] , один сверху и один снизу цилиндра. Изогнутая сторона на самом деле большой [[прямоугольник | квадрат | эллипс]] 

 * {.reveal(when="blank-0 blank-1")} Два круга каждый имеют площадь _{x-equation.small(solution="π r^2" keys="+ × π sup" short-var)}_ , * {.reveal(when="eqn-0")} Высота прямоугольника _{x-equation.small(solution="h" keys=" " short-var)}_ _{span.reveal(when="eqn-1")} и ширина прямоугольника равна [[окружности | диаметр | касательная]] окружностей:_ _{x-equation.small.reveal(when="blank-2" solution="2 π r" keys="+ × π sup" short-var)}_ , 

::: column(width=320)

    x-solid(size=340 style="margin: -10px;")
    x-slider(steps=100 speed=0.5)

:::

---
> id: cylinder-surface-1

 Это означает, что общая площадь поверхности цилиндра с радиусом _r_ и высотой _h_ определяется как 

{.text-center}`A =` _{x-equation(solution="2 π r^2 + 2 π r h" keys="+ − × ÷ π frac sup brackets" short-var)}_ , 

---
> id: cylinder-real-life

    figure: x-img(src="images/cylinders.jpg" width=460 height=125)

 Цилиндры можно найти повсюду в нашем мире - от банок содовой до туалетной бумаги или водопроводных труб. Можете ли вы вспомнить другие примеры? 

 _Газометр_ выше имел радиус 35 метров и высоту 120 метров. Теперь мы можем рассчитать, что его объем составляет примерно [[461 000 ± 1000]] `"m"^3` и его площадь поверхности составляет примерно [[34,080 ± 100]] `"m"^2` , 

---
> id: cone

### Конусы 

::: column.grow

 [__Конус__](gloss:cone) - это трехмерное твердое тело с круговым __{.m-red} база__ . Его сторона «сужается вверх», как показано на рисунке, и заканчивается в одной точке, называемой __{.m-green} вершина__ 

 __{.m-red} радиус__ конуса является радиусом круглого основания, а __{.m-blue} Высота__ конуса - это перпендикулярное расстояние от основания до вершины. 

 Как и другие формы, которые мы встречали раньше, вокруг нас повсюду шишки: конусы мороженого, дорожные конусы, некоторые крыши и даже рождественские елки. О чем еще можно думать? 

::: column(width=280)

    x-solid(size=280)

:::

::: column(width=120 parent="padded-thin")

    x-img(src="images/ice-cream.jpg" width=120 height=120 lightbox)

::: column(width=120 parent="padded-thin")

    x-img(src="images/traffic.jpg" width=120 height=120 lightbox)

::: column(width=120 parent="padded-thin")

    x-img(src="images/roof.jpg" width=120 height=120 lightbox)

::: column(width=120 parent="padded-thin")

    x-img(src="images/christmas.jpg" width=120 height=120 lightbox)

::: column(width=120 parent="padded-thin")

    x-img(src="images/tipi.jpg" width=120 height=120 lightbox)

:::

---
> id: cone-volume

#### Объем Конуса 

::: column.grow

 Ранее мы нашли объем цилиндра, аппроксимировав его с помощью призмы. Точно так же мы можем найти объем конуса, аппроксимируя его с помощью [__пирамиды__](gloss:pyramid) . 

 Здесь вы можете увидеть ${n}{n|5|3,18,1} пирамида По мере увеличения числа сторон пирамида начинает все больше походить на конус. На самом деле, мы можем думать о конусе как о пирамиде с _бесконечным числом_ сторон! 

::: column(width=280)

    x-solid(size=280 style="margin: -44px 0 -20px 0")

:::

---
> id: cone-volume-1

 Это также означает, что мы также можем использовать уравнение для объема: `V = 1/3 "base" × "height"` , Основание конуса представляет собой круг, поэтому объем конуса с радиусом _r_ и высотой _h_ равен 

{.text-center}`V =` _{x-equation(solution="1/3 π × r^2 h" keys="+ − × ÷ π frac sup brackets" short-var hints="cone-volume-hint1 cone-volume-hint2")}_ 

---
> id: cone-circumscribed

 Обратите внимание на сходство с уравнением для объема цилиндра. Представьте себе, что _вокруг_ конуса нарисован цилиндр с таким же основанием и высотой - это называется __описанным цилиндром__ . Теперь конус займет ровно [[треть | половина | одна четверть]] объема цилиндра: 

    figure: x-solid(size=280)

---
> id: cone-hilbert

{.i.lgrey} Примечание: вы можете подумать, что бесконечное множество крошечных граней в качестве приближения немного «неточно». Математики потратили много времени, пытаясь найти более простой способ расчета объема конуса. В 1900 году великий математик [Дэвид Гильберт](bio:hilbert) даже назвал его одной из 23 самых важных нерешенных проблем математики! Сегодня мы знаем, что это на самом деле невозможно. 

---
> id: oblique-cone
> goals: slide

::: column.grow

 Точно так же, как цилиндр, конус не должен быть «прямым». Если вершина находится прямо над центром основания, у нас есть __правый конус__ . В противном случае мы называем это __косым конусом__ . 

 Еще раз, мы можем использовать принцип Кавальери, чтобы показать, что все наклонные конусы имеют одинаковый объем, если они имеют одинаковое основание и высоту. 

::: column(width=280)

    x-solid(size="280,240" static)
    x-gesture(target="#oblique-cone x-solid" slide="60,0")

:::

---
> id: cone-surface

#### Площадь поверхности конуса 

::: column.grow

 Найти площадь поверхности конуса немного сложнее. Как и прежде, мы можем распутать конус в его сети. Переместите ползунок, чтобы увидеть, что происходит: в этом случае мы получаем один круг и один [[сектор круга | сегмент круга | дуга окружности]] 

{.reveal(when="blank-0")} Теперь нам нужно просто сложить площадь обоих этих компонентов. __{.m-yellow} Основание__ представляет собой круг с радиусом _r_ , поэтому его площадь 

{.text-center.reveal(when="blank-0")}`pill(A_"Base","yellow","circle") =` _{x-equation.small(solution="π r^2" keys="+ × π sup" short-var)}_ , 

::: column(width=320)

    x-solid(size=340 style="margin: -32px -10px -10px;")
    x-slider(steps=100 speed=0.5)

:::

---
> id: slant-height

::: column.grow

 Радиус __{.m-green} сектор__ равен расстоянию от края конуса до его вершины. Это называется [{.pill.green.b} наклонная высота _s_](target:s) конуса, а не такая, как у нормального [{.pill.blue.b} высота _ч_](target:h) . Мы можем найти наклонную высоту, используя [Пифагор](gloss:pythagoras-theorem) : 

 | `s^2` | `=` | _{x-equation(solution="r^2 + h^2" keys="+ × π sup")}_ | | `s` | `=` | _{x-equation(solution="sqrt(r^2 + h^2)" keys="+ × sup sqrt")}_ | {.eqn-system}

::: column(width=280)

    x-geopad.sketch.no-background(width=280 height=200): svg
      circle(x="point(140, 10)" name="a" hidden)
      circle(x="point(140, 170)" name="b" hidden)
      circle(x="point(220, 170)" name="c" hidden)
      circle(x="point(60, 170)" name="d" hidden)
      ellipse(cx=140 cy=172 rx=81 ry=20)
      path(x="angle(a,b,c)" size=12)
      path(x="triangle(a,c,d)")
      path.yellow(x="segment(b,c)" label="r" target="r")
      path.green(x="segment(a,c)" label="s" target="s")
      path.blue(x="segment(a,b)" label="h" target="h")

:::

---
> id: cone-surface-1

::: column.grow

 [{.pill.red} длина дуги](target:arc) сектора равна [[окружности | диаметр | дуга]] [{.pill.yellow} база](target:base) : _{span.reveal(when="blank-0")}`2 π r` , Теперь мы можем найти площадь сектора, используя [формулу, которую](gloss:circle-sector) мы вывели в предыдущем разделе:_ 

::: x-equation-system.reveal(when="blank-0" steps="π s^2 * ( 2 π r ) / (2 π s) | π r s" hints="cone-surface-1|cone-surface-1")

 | `pill(A_"Sector","green","sector")` | `=` | `pill(A_"Circle","teal","circle") × pill("arc","red","arc") / pill("circumference","teal","circumference")` | | | `=` | _{x-equation(solution="π r sqrt(r^2 + h^2)" fns="/" substitutions="s: sqrt(r^2 + h^2)" keys="+ − × ÷ π frac sup sqrt" short-var)}_ | 

:::

::: column(width=280)

    x-geopad.sketch.no-background(width=280 height=300 style="margin-top: -20px"): svg
      circle(x="point(140,110)" name="c1" hidden)
      circle(x="point(140,250)" name="c2" hidden)
      circle(x="point(235,141.5)" name="a" hidden)
      circle(x="point(45,141.5)" name="b" hidden)
    
      path.yellow.fill.light(x="circle(c2, 40)" target="base")
      path.yellow(x="circle(c2, 40)" target="base")
      path.yellow(x="segment(c2,point(180, 250))" label="r" target="base")
      path.red.thick.reveal(when="blank-0" animation="draw" duration=1500 x="circle(c2, 40)")
    
      path.teal.fill.light(x="circle(c1, 100)" name="circ" target="circle")
      path.green.fill.light(x="sector(c1, a, 2.5)" target="sector circle")
    
      path.green(x="segment(c1, a)" label="s")
      path.green(x="segment(c1, b)" label="s")
      path.red.thick(x="arc(c1, a, 2.5)" target="arc")
      path.teal.thick.transparent(x="circle(c1, 100)" target="circumference")

:::

---
> id: cone-surface-2

 Наконец, мы просто должны сложить площадь __{.m-yellow} база__ и площадь __{.m-green} сектора__ , чтобы получить общую площадь поверхности конуса: 

{.text-center}`A =` _{x-equation(solution="π r^2 + π r sqrt(h^2 + r^2)" keys="+ − × ÷ π frac sup sqrt" short-var)}_ 

---
> id: sphere

### Spheres 

::: column.grow

 [__Сфера__](gloss:sphere) - это трехмерное тело, состоящее из всех точек, находящихся на одинаковом расстоянии от заданного __{.m-green} центр _C.___ Это расстояние называется __{.m-red} радиус _r___ сферы. 

 Вы можете думать о сфере как о «трехмерном [круге](gloss:circle) ». Как и круг, сфера также имеет __{.m-blue} диаметр _d___ , который в [[два раза | на половину]] длины радиуса, а также аккордов и секущих. 

::: column(width=240)

    x-solid(size=240)

:::

---
> id: sphere-1

{.r} В [предыдущем разделе](/course/circles/tangets-chords-arcs#eratosthenes-1) вы узнали, как греческий математик [Эратосфен](bio:eratosthenes) вычислил радиус Земли, используя тень от полюса - он составлял 6 371 км. Теперь давайте попробуем найти общий объем Земли и площадь поверхности. [Продолжать](btn:next) 

---
> id: sphere-volume

#### Объем сферы 

 Чтобы найти объем сферы, мы снова должны использовать принцип Кавальери. Начнем с полушария - сферы, разрезанной пополам вдоль экватора. Нам также нужен цилиндр с таким же радиусом и высотой, как у полушария, но с перевернутым в середине перевернутым конусом. 

 Перемещая ползунок ниже, вы можете видеть поперечное сечение обеих этих фигур на определенной высоте над основанием: 

::: column(width=240)

    x-solid(size=240 style="margin: -24px 0 10px")
    
    x-geopad.r.no-background(width=220 height=120): svg
      circle(x="point(110,110)" name="c1")
      circle(x="c1.shift(0,-100*h)" name="h1")
      circle(x="h1.shift(-100 * sqrt(1-h*h),0)" name="a1")
    
      path.yellow.fill.light(x="triangle(c1,a1,h1)" target="tri")
      path(x="arc(c1,point(10,c1.x),pi)")
      path(x="segment(point(10,c1.x),point(210,c1.x))")
      path.green.thin(x="segment(c1,a1)" label="r" target="r tri")
      path.blue.thin(x="segment(h1,c1)" label="h" target="h h1 tri")
      path.red.thick(x="segment(h1,a1)" label="x" target="x tri")
      path.red.thick(x="segment(h1,point(220-a1.x,a1.y))")

::: column(width=240)

    x-solid(size=240 style="margin: -24px 0 10px")
    
    x-geopad.r.no-background(width=220 height=120): svg
      circle(x="point(10,10)" name="a2" hidden)
      circle(x="point(210,10)" name="b2" hidden)
      path(x="polygon(a2,b2,point(210,110),point(10,110))")
    
      circle(x="point(110,110)" name="c2")
      circle(x="c2.shift(0,-100*h)" name="h2")
      circle(x="h2.shift(-100*h,0)" name="x2")
    
      path.thin(x="segment(a2,c2)")
      path.thin(x="segment(b2,c2)")
      path.blue.thin(x="segment(h1,c1)" label="h" target="h")
      path.blue.thin(x="segment(h1,point(110-100*h,h2.y))")
      path.red.thick(x="segment(point(10,h2.y),point(110-100*h,h2.y))")
      path.red.thick(x="segment(point(110+100*h,h2.y),point(210,h2.y))")

:::

    x-slider(steps=100)

{.reveal(when="slider-0")} Попробуем найти площадь поперечного сечения обоих этих тел на расстоянии [{.pill.blue} высота _h_](target:h) над основанием. 

::: column.grow

{.reveal(when="slider-0")} Сечение полушария всегда [[круг | кольцо | цилиндр]] 

{.reveal(when="blank-0")} [{.pill.red} радиус _х_](target:x) поперечного сечения является частью [{.pill.yellow} прямоугольный треугольник](target:tri) , поэтому мы можем использовать [Пифагор](gloss:pythagoras-theorem) : 

::: .reveal(when="blank-0")

{.text-center}`pill(r^2,"green","r") = pill(h^2,"blue","h1") + pill(x^2,"red","x")` , 

 Теперь площадь поперечного сечения 

    x-equation-system(steps="π x^2" hints="circle-cross-sec")
      table: tr
        td: em A
        td =
        td: x-equation(solution="π * (r^2 - h^2)" substitutions="x: sqrt(r^2 - h^2)" fns="sqrt" keys="+ − × ÷ π sup sqrt brackets" short-var)

:::

::: column.grow.reveal(when="eqn-0")

 Поперечное сечение вырезаемого цилиндра всегда является [[кольцом | круг | конус]] 

::: .reveal(when="blank-1")

 Радиус отверстия составляет _h_ . Мы можем найти площадь кольца, вычтя площадь отверстия из области большего круга: 

 | _A_ | = | `π r^2 - π h^2` | | | = | `π (r^2 - h^2)` | {.eqn-system}

:::

:::

---
> id: sphere-volume-1

 Похоже, что оба тела имеют одинаковую площадь поперечного сечения на каждом уровне. По принципу Кавальери, оба тела должны также иметь одинаковый [[объем | площадь поверхности | окружность]] ! _{span.reveal(when="blank-0")} Мы можем найти объем полушария, вычитая объем [цилиндра](gloss:cylinder-volume) и объем [конуса](gloss:cone-volume) :_ 

::: x-equation-system.reveal(when="blank-0" steps="π r^3 - 1/3 π r^3" hints="sphere-volume")

 | `V_"Hemisphere"` | = | `V_"Cylinder" - V_"Cone"` | | | = | _{x-equation(solution="2/3 π r^3" keys="+ − × ÷ π frac sup brackets" short-var)}_ | 

:::

---
> id: sphere-volume-2

 Сфера состоит из [[двух]] полушарий, _{span.reveal(when="blank-0")} это означает, что его объем должен быть_ 

{.text-center.reveal(when="blank-0")}`V = 4/3 π r^3` , 

---
> id: earth-volume
> goals: numbers

::: column.grow

 Земля (приблизительно) сфера с радиусом 6 371 \ км. Поэтому его объем 

 | `V` | `=` | _{x-equation(solution="4/3 pi × 6371^3" keys="+ − × ÷ π frac sup sqrt" short-var)}_ | | | `=` | _{span.numbers} 1_ `"km"^3` | {.eqn-system}

{.reveal(when="numbers")} Средняя плотность Земли `5510 "kg/m"^3` , Это означает, что его общая масса 

{.text-center.reveal(when="numbers")}`"Mass" = "Volume" × "Density" ≈ 6 × 10^24 "kg"`

{.reveal(when="numbers")} Это 6, за которыми следуют 24 нуля! 

::: column(width=280)

    x-solid(size=280 rotate="0.5")

:::

---
> id: sphere-sum

 Если вы сравните уравнения для объема цилиндра, конуса и сферы, вы можете заметить одно из наиболее удовлетворительных соотношений в геометрии. Представьте, что у нас есть цилиндр с той же высотой, что и диаметр его основания. Теперь мы можем идеально вписать и конус, и сферу внутри: 

::: column.r(width=220)

    x-solid(size=220 style="margin-top: -20px")
    .large-op.reveal(when="blank-0" animation="pop") +

{.text-center} Этот конус имеет радиус `r` и высота `2r` , Его объем _{x-equation.small(solution="2/3 π r^3" keys="× π sup frac" short-var)}_ 

::: column.r(width=220)

    x-solid(size=220 style="margin-top: -20px")
    .large-op.reveal(when="blank-0" animation="pop") =

{.text-center} Эта сфера имеет радиус `r` , Его объем _{x-equation.small(solution="4/3 π r^3" keys="× π sup frac" short-var)}_ 

::: column(width=220)

    x-solid(size=220 style="margin-top: -20px")

{.text-center} Этот цилиндр имеет радиус `r` и высота `2r` , Его объем _{x-equation.small(solution="2 π r^3" keys="× π sup frac" short-var)}_ 

:::

{.reveal(when="eqn-0 eqn-1 eqn-2")} Обратите внимание, как, если мы [[сложим | вычитать | Умножив]] объем конуса и сферы, мы получим именно объем цилиндра! 

---
> id: sphere-maps
> goals: move projection

#### Площадь поверхности сферы 

 Найти формулу для площади поверхности сферы очень сложно. Одна из причин заключается в том, что мы не можем открыть и «сплющить» поверхность сферы, как мы делали это раньше для конусов и цилиндров. 

 Это особая проблема при попытке создания карт. Земля имеет изогнутую трехмерную поверхность, но каждая печатная карта должна быть плоской и двухмерной. Это означает, что географы должны обманывать: растягивая или прижимая определенные области. 

 Здесь вы можете увидеть несколько разных типов карт, называемых __проекциями__ . Попробуйте переместить красный квадрат, и посмотреть , что эта область на _самом деле_ выглядит на земном шаре: 

    figure
      x-select.tabs
        .projection(data-name="mercator") Mercator
        .projection(data-name="cylindrical") Cylindrical
        .projection(data-name="robinson") Robinson
        .projection(data-name="mollweide") Mollweide
      .box.no-padding.sphere-maps
        .left
          svg.sphere-map(width=240 height=240 viewBox="0 0 240 280")
            path.outline
            path.grid
            path.land
            path.map-select
        .right
          svg.sphere-map#projection(width=440 height=280 viewBox="0 0 440 280")
            path.outline
            path.grid
            path.land
            rect.map-select(x="-24" y="-24" width=48 height=48 style="cursor: move")
          p.caption As you move the square on the map, notice how the size and shape of the #[em actual] area changes on the three-dimensional globe.
    x-gesture(target="#projection" slide="50, 20")

---
> id: sphere-surface

 Чтобы найти площадь поверхности сферы, мы можем еще раз приблизить ее, используя другую форму - например, многогранник с множеством граней. По мере увеличения числа граней многогранник становится все больше и больше похожим на сферу. 

{.todo} СКОРО: доказательство поверхности сферы 

    // If we connect the small polygons to the center of the sphere, we get
    // lots of small pyramids pointing inwards. The diagram shows one of these pyramids
    // in red. The height of each pyramid is the [[radius|diameter]] of the sphere.
    
    // Here is a
    // volume = lots of cones = 1/3 * radius * lots of bases = 1/3 * radius * surface area
    
    // And therefore,
    // surface area = 3 * volume / radius = 
    
    // In other words, the surface area of a sphere with radius _r_ is `S = 4 π r^2`.
    
    // ---
    // > id: earth-surface
    // 
    // surface of earth

---

## Конические сечения 

> section: conic-sections
> id: conics
> goals: ellipse parabola hyperbola

 Круг является одной из четырех различных форм, которые можно создать, используя «ломтики» через [конус](gloss:cone) . Это можно продемонстрировать с помощью светового конуса факела: 

    x-conic-section
    x-scale-box(width=760).conics
      .row
        .active
          p.no-voice: strong Circle
          include svg/circle.svg
        .hide
          p.no-voice: strong Ellipse
          include svg/ellipse.svg
        .hide
          p.no-voice: strong Parabola
          include svg/parabola.svg
        .hide
          p.no-voice: strong Hyperbola
          include svg/hyperbola.svg

---
> id: conics-1

 Если вы направите факел вертикально вниз, вы увидите [[круг | эллипс | овал]] света. _{span.reveal(when="blank-0")} Если вы наклоните конус, вы получите [__эллипс__](gloss:ellipse) . Если вы наклоните его еще дальше, вы получите [__параболу__](gloss:parabola) или [__гиперболу__](gloss:hyperbola) ._ 

---
> id: conics-2

::: column.grow

 В совокупности эти четыре формы называются [__коническими сечениями__](gloss:conic-section) . Хотя все они выглядят очень по-разному, они тесно связаны между собой: на самом деле все они могут быть получены с использованием одного и того же уравнения! 

 Конические сечения были впервые изучены древнегреческим математиком [Аполлонием Пергским](bio:apollonius) , который также дал им свои необычные имена. 

 На последующих курсах вы узнаете гораздо больше о параболах и гиперболах. А пока давайте подробнее рассмотрим эллипс. 

::: column(width=300)

    x-img(src="images/conics.svg" width=300 height=340)

:::

---
> id: ellipses

### Эллипс 

 Эллипс выглядит почти как «вытянутый круг». На самом деле, вы можете думать об этом как о круге с _двумя центрами_ - они называются __фокусными точками__ . Точно так же, как каждая точка на круге имеет одинаковое расстояние от своего центра, каждая точка на эллипсе имеет одинаковую _сумму расстояний_ до двух фокусных точек. 

 Если у вас есть длинная строка, соединенная с двумя фиксированными точками, вы можете нарисовать идеальный эллипс, отследив максимальный радиус действия строк: 

{.todo} Скоро: рисование эллипсов 

    // ---
    // > id: ellipses-1
    // You can also move the focal points around. Notice how, if they are further
    // apart, the ellipse will be [[more|less]] elongated. If they are close together,
    // it will look almost like a [[circle|parabola|trapezium]].

---
> id: ellipses-2
> goals: v0 v1 v2 v3

 Есть много других физических представлений о том, как вы можете нарисовать эллипс: 

::: column(width=320 parent="padded-thin")

    x-video(src="images/gears.mp4" poster="images/gears.jpg" width=320 height=230 credit="© Pavel Boytchev, Elica Logo")
    p.caption Gears

::: column(width=320)

    x-video(src="images/trammel.mp4" poster="images/trammel.jpg" width=320 height=230 credit="© Pavel Boytchev, Elica Logo")
    p.caption Trammel

::: column(width=320)

    x-video(src="images/disk.mp4" poster="images/disk.jpg" width=320 height=230 credit="© Pavel Boytchev, Elica Logo")
    p.caption Disk

::: column(width=320)

    x-video(src="images/swing.mp4" poster="images/swing.jpg" width=320 height=230 credit="© Pavel Boytchev, Elica Logo")
    p.caption Swing

:::

---
> id: orbits

### Планетарные Орбиты 

::: column.grow

 Возможно, вы помните с самого начала этого курса, что древнегреческие астрономы считали, что Земля находится в центре вселенной и что солнце, луна и планеты движутся вокруг Земли по круговым орбитам. 

 К сожалению, астрономические наблюдения неба не совсем это подтверждают. Например, солнце казалось больше в течение некоторых частей года и меньше в другие. На окружности каждая точка должна иметь [[одинаковую | увеличивающийся | уменьшающееся]] расстояние от его центра. 

::: column(width=330)

    x-img(src="images/hipparchus.jpg" width=330 height=280 lightbox)

{.caption} Греческий астроном Никпейский Гиппарх 

:::

---
> id: epicycles
> goals: play

 Чтобы исправить это, астрономы добавили __эпициклы__ к своей модели солнечной системы: планеты движутся по большому кругу вокруг Земли, одновременно вращаясь по меньшему кругу. Несмотря на свою сложность, эта модель была самой широко принятой в нашей вселенной на протяжении более 1000 лет: 

::: column(width=320)

    .r
      svg(width=320 height=320)
        circle.large-circle(cx=160 cy=160 r=120 fill="none" stroke="#ccc" stroke-width="2px")
        circle.small-circle(cx=280 cy=160 r=30 fill="none" stroke="#ccc" stroke-width="2px")
        path(fill="none" stroke="#fd8c00" stroke-width="3px" opacity="0.8" stroke-linejoin="round")
        circle(cx=160 cy=160 r=15 fill="#0f82f2")
        circle.earth(cx=310 cy=160 r=10 fill="#fd8c00")
      x-play-btn

{.caption} Эта планета делает ${n}{n|6|2,12,1} вращения вокруг малого круга ( __эпицикла__ ) за один оборот вокруг большого круга ( __семяпровода__ ). 

::: column(width=320)

    x-img(src="images/epicycles.jpg" width=320 height=320)

{.caption} Рисунок 16-го века эпициклов в __геоцентрической модели__ . Греческое слово «plantes» означает «странники». 

:::

---
> id: kepler
> goals: play

::: column.grow

 Со временем люди осознали, что Земля была лишь одной из многих планет, вращающихся вокруг Солнца ( __гелиоцентрическая модель__ ), но только в 1609 году астроном [Иоганн Кеплер](bio:kepler) обнаружил, что планеты действительно движутся по _эллиптическим орбитам_ . 

 Солнце находится в одной из двух фокусных точек этих эллипсов. Планеты ускоряются по мере приближения к Солнцу и замедляются по мере удаления. 

::: column(width=320)

    .r
      svg(width=320 height=240)
        path.sweep(fill="#0f82f2" opacity="0.25")
        path.orbit(fill="none" stroke="#ccc" stroke-width="3px" opacity="0.8" stroke-linejoin="round")
        circle.earth(cx=280 cy=120 r=10 fill="#0f82f2")
        circle(cx=220 cy=120 r=15 fill="#fd8c00")
        circle(cx=100 cy=120 r=4 fill="#ccc")
      x-play-btn

:::

---
> id: newton
> goals: apple

 Несколько десятилетий спустя [Исаак Ньютон](bio:newton) смог доказать наблюдения Кеплера, используя свои недавно разработанные законы [__гравитации__](gloss:gravity) . Ньютон осознал, что между любыми двумя массами во вселенной существует сила, похожая на притяжение между двумя магнитами. 

 Гравитация - это то, что заставляет все падать на землю, а гравитация - это то, что заставляет планеты вращаться вокруг Солнца. Только огромная скорость, с которой движутся планеты, предотвращает их падение прямо на солнце. 

::: column(width=280)

    // Source: https://www.flickr.com/photos/hikingartist/6217869031
    .newton.interactive
      img(src="images/newton-2.jpg" width=280 height=370)
      img.over(src="images/newton-1.jpg" width=280 height=370)
      img.apple(src="images/newton-apple.png" width=30 height=40)
      .credit Frits Ahlefeldt
    x-gesture(target=".newton" offset="20,-120")

::: column.grow

 Используя законы Ньютона, вы можете определить путь, по которому идут объекты при движении под действием силы тяжести. Оказывается, что планеты движутся по эллипсам, но другие объекты, такие как кометы, могут перемещаться по [параболическим](gloss:parabola) или [гиперболическим](gloss:hyperbola) путям: они летят близко к солнцу, прежде чем развернуться и выстрелить во вселенную, чтобы никогда не вернуться назад. 

 Согласно легенде, падающее яблоко вдохновило Ньютона задуматься о гравитации. Он был одним из самых влиятельных ученых всех времен, и его идеи формировали наше понимание мира в течение почти 300 лет - пока Альберт Эйнштейн не открыл относительность в 1905 году. 

:::
