# Виртуальная и дополненая реальность
Отчет по лабораторной работе #2 выполнил(:
- Попович Иван Алексеевич
- РИ-300022
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | # | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- 
- 
- 


Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы
изучить работу пакета Unity XR, настройку VR оборудования, запуск VR проекта через настроенное оборудование.

## Задание 1
### Пошагово выполнить каждый пункт раздела "ход работы" с описанием и примерами реализации задач
Ход работы:
1)	Создать новый проект из шаблона 3D – Core;
2)	Откройте вкладку edit -> project settings;
3)	установить XR plugin Managment;
4)	Создать объект Cube;
5)	Настройте XR Plugin Management на работу через SDK OpenXR;
6)	Настройте режим рендера VR на каждый глаз;
7)	Добавить поддержку контроллеров вашего оборудования;
8)	Через вкладку Windows -> Pacage Manager добавьте и установите пакет
com.unity.xr.interaction.toolkit;
9)	Импортируйте Starter Assets из установленного пакета;
10) Настройте Input system на основе импортированного Starter Assets;
11) Скачайте и установите Steam и Steam VR;
12) Настройте и подключите к PC ваше VR оборудование;
13) Вернитесь в Unity и настройте запуск проекта через SteamVR;
14) Добавьте объект Plane;
15) Добавьте на сцену объект XR-Orig (Action Base);
16) На объект XR Interaction Manager создайте компонент Input Action
Manager;
17) Добавьте в Input Action Manager настроенный Input System;
18) Запустите проект и убедитесь, что он воспроизводится на VR
оборудовании.

### Ход выполнения работы

Код скрипта, который отвечает за соприкосновения сферы и куба, конкретнее отвечает за то, чтобы
объект "куб" перекрашивался при активации и деактивации триггера. Также код выводит сообщения в консоль.
```c#

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CheckCollider : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        
    }

    private void OnTriggerEnter(Collider other) {
        Debug.Log(other.gameObject.name);
        other.GetComponent<Renderer>().material.SetColor("_Color", Color.green);
    }

    private void OnTriggerExit(Collider other) {
        Debug.Log("Завершил столкновение с " + other.gameObject.name);
        other.GetComponent<Renderer>().material.SetColor("_Color", Color.red);
    }
}


```



## Задание 2
### Продемонстрируйте на сцене в Unity следующее:
 - Что значит X в аббревиатуре XR?
 - Какие SDK поддерживает XR Plugin Management по Default?

### Ход выполнения работы
Ответ на вопрос 1:
Координаты дочернего объекта берут 0 в точке родительского. Если просто перетащить объект и сделать его родительским, то его координаты сменят числовое значение относительно всей сцены,
но объект положения не поменяет

Ответ на вопрос 2:
Поэксперементировав над разными параметрами RigidBody, понял, что поле с параметром UseGravity отвечает за гравитацию объеекта.
IsKinematic при включении отвечает за то, что на объект больше не действует никакая физиак, так например, если его толкнули, или заставили вращаться, то действие сли просто прекратится
Так, поскольку надо было выполнить три пункта, то я ещё настраивал вес объекта. Как оказалось, этот параметр влияет на импульс объекта при соприкосновенни. Так, если вес объекта 0, то после удара о другой объект, на этот друго объект не будет действовать никакая сила.
## Выводы

Во время выполнения этой работы, я научился самым азам обращения с Unity. Создавать объекты, менять их настройку. Также узнал за что именно отвечают некоторые пункты в его настройке. Также научился базовой работе с триггерами и создавать скрипты.

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
