# Нахождение кратчайшего пути в взвешенном ориентированном ациклическом графе

Представим этот граф в массиве ребер, который является массивом `[x, y, weight]`, где -  `x`- начальная вершина, `y` - конечная вершина, `weight` - вес.

    const peaks = [
    [1, 2, 5], [1, 4, 3], [1, 10, 100], [1, 3, 1],
    [2, 5, 1], [2, 7, 15],
    [3, 5, 3], [3, 6, 1],
    [4, 10, 23],
    [5, 9, 10],
    [6, 8, 1],
    [7, 9, 1],
    [8, 7, 1],
    [9, 10, 1],
    [10, 999, 999],
    ];

Для неотрицательного числа `i` , учитывая, что любой путь содержит не более `i` ребер, каков кратчайший путь от начальной вершины до других вершин?

Начиная с базового случая, где `i` равно `0`, в этом случае расстояние до всех вершин, кроме начальной, бесконечно, а расстояние до начальной вершины равно `0`. Для `i` от `1 `до `vertices-count - 1`(самый длинный кратчайший путь к любой вершине содержит большинство ребер, при условии, что нет отрицательного круга веса), мы перебираем все ребра:
для каждого `peaks` мы вычисляем новое расстояние `peaks[2] + distance-to-vertex-peaks[0]`, если новое расстояние меньше `distance-to-vertex-peaks[1]`, мы обновляем `distance-to-vertex-peaks[1]` с новым расстоянием.

Результат: 


![](https://sun9-48.userapi.com/c854328/v854328256/1ec1fd/yrhbNPEUQ7c.jpg)
