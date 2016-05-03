---
title:  "Плохой код #2"
categories: JavaScript
date:   2016-05-01 11:00:00 +0300
author_name: "Евгений Бовыкин"
author: missingdays
type: exercise
identifier: exercise-bad-code-2

description: "Исправляем плохой код. Комментарии"

tags: [javascript]
---

Комментарии в коде крайне важны. Еще важнее хорошие комментарии. Однако всегда ли они нужны? Стоит ли комментировать каждую строчку? Скорее всего нет. Но где проходит граница, что нужно комментировать, а что нет? И насколько подробным должен быть комментарий? В этой статье попробуем разобраться.

Попробуйте определить, нужны ли комментарии в каждом из отрывков кода, и если да, то насколько подробны они должны быть? Стоит ли что-нибудь убрать, изменить, добавить?

> Для упрощения допутим, что функции в данном не связаны, т.е. не находятся в одном модуле, коде, и вообще не знают друг о друге. Не заморачивайтесь, стоит ли вместо Math.random использовать в них getRandomNumber - думайте о комментариях.

{% highlight javascript %}

// Возращает случайное число
function getRandomNumber(){
    return Math.random();
}

// Возращает случайное число от min до max
function getRandomInRange(min, max) {
  return Math.random() * (max - min) + min;
}

function getRandomIntInRange(min, max){
    return Math.floor(Math.random() * (max - min)) + min;
}

// Возращает случайное число от min (включительно) до max
function getRandomIntInRangeInclusive(min, max){
    return Math.floor(Math.random() * (max - min + 1)) + min;
}

{% endhighlight %}

В нижнем примере приведен только заголовок функции, ее реализация нас пока не интересует (но мы несомненно доберемся до нее).

{% highlight javascript %}

/**
 * Генерирует простые числа в диапазоне до максимального значения, заданного
 * пользователем, по алгоритму "Решето Эратосфена".
 * ---
 * Эратосфен Киренский. 276 год до н.э., Ливия -- * 194 год до н.э., Александрия.
 * Первый ученый, вычисливший длину земного меридиана. Известен своими работами о календарях
 * о календарях с високосным годом, заведовал Александрийской библиотекой.
 * ---
 * Алгоритм весьма прост. Берем массив целых чисел, начиная с 2, и вычеркиваем из него все числа,
 * кратные 2. Находим следующее невычеркнутое число и вычеркиваем все его кратные. Повторяем до тех
 * пор, пока не дойдем до квадратного корня верхней границы диапазона.
 */

function generatePrimes(maxBound){
    // ...
}

{% endhighlight %}

И еще один, довольно абстрактный, но полезный пример.

{% highlight javascript %}

/*
 * Начать с массива, размер которого достаточен для хранения всех пикселов
 * (плюс байты фильтра), плюс еще 200 для данных заголовка
 * Инициализируем его максимумом.
 */

let pngBytes = []; 

for(let i = 0; i < (width+1)*height*3) + 200; i++){
    pngBytes.push(16777215);
}

{% endhighlight %}

И напоследок

{% highlight javascript %}

// Опыт для поднятия текущего уровня
function getExpForLevel(level){
    
    // Сумма чисел от 1 до n умножить на "дополнительный коэффициент"
    // и деленное на два

    return n*(n+1) * ((n+10) / 10) / 2;
}

{% endhighlight %}