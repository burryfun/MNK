# Интерполяция методом наименьших квадратов используя полином 5 степени

### Задание

Реализовать в matlab метод МНК для конечного набора значений, используя полином 5 степени, без использования стандартных функций lsqcurvefit() или polyfit(). На графике должны отображаться заданные точки и аппроксимирующая их функция.

### Входные данные

Исходная функция задается как набор значений y_p на интервале x_p, далее к исходной функции добавляются случайные числа.

Полученные значения отдаем на вход функции getInterpFunction(x_p, y_p_random, degree), где degree = 5 - степень полинома.

### Результат

На выходе функции getInterpFunction получаем набор коэффициетов полинома и массив из 100 точек полученной функции.

#### Исходная функция - полином 6 степени на интервале (-2,2). Кол-во точек = 40

```
x_p = -2:0.1:2;
y_p = 0.5*x_p.^6-0.9*x_p.^4+0.13*x_p.^3-6*x_p.^2+0.4*x_p+5;
% Добавление нормального распределения
y_p_random = zeros(1, length(y_p));
for i = 1:length(y_p)
    r1 = random('Normal',0,1);
    y_p_random(i) = y_p(i) + r1;
end
```
![](/images/image1.png)

#### Исходная функция - полином 5 степени на интервале (-1,3). Кол-во точек = 40

```
x_p = -1:0.1:3;
y_p = 0.5*x_p.^5-0.9*x_p.^4+0.13*x_p.^3-6*x_p.^2+0.4*x_p+5;
% Добавление нормального распределения
y_p_random = zeros(1, length(y_p));
for i = 1:length(y_p)
    r1 = random('Normal',0,1);
    y_p_random(i) = y_p(i) + r1;
end
```
![](/images/image2.png)
