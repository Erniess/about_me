---
layout: post
title: "Тестовое задание №1"
type: project
---

## Задача на тестирование.  
К вакансии Инженер по тестированию беспилотных транспортных [средств](https://yandex.ru/jobs/vacancies/testing/test_engineer_drone/)

### Задача  
Вам необходимо протестировать новую версию модуля локального планировщика маршрутов (motion planning) и принять решение о выпуске ее в production. 
Планировщик маршрута работает следующим образом: на вход модуль принимает текущее местоположение, карту объектов вокруг автомобиля и пункт назначения. 
На выходе выдает траекторию (наборы точек), которые впоследствии модуль управления автомобилем преобразовывает в углы поворота руля и ускорения. 
Основная задача планировщика — выдать оптимальные и безопасные траектории до пункта назначения. Предложите набор тест-кейсов, по которым бы вы 
проводили проверку.  

## Решение
Прежде всего убеждаемся, что автомобиль технически исправен, находится в безопасном месте, все системы полностью загружены, ошибки отсутствуют, 
локализация и положение автомобиля соответствуют действительности. Местоположение в пределах карты дорог.  

Сначала проверяем базовые позитивные сценарии.  
1. Построение маршрута на пустой дороге:  
  1.1 по прямой  
  1.2 разворот  
  1.3 левый поворот  
  1.4 правый поворот  
  1.5 перестроение  
  1.6 ветвление полос  
  1.7 слияние полос  
  1.8 пересечение полос  
  1.9 удержание полосы  
  1.10 смена маршрута  

Затем проверка основной функциональности с дополнительными параметрами.  
2. Построение маршрута с объездом объекта на однополосной/многополосной дороге. Тип и положение объекта:  
  2.1 cтатический/припаркованный динамический:  
      2.1.1 у края полосы  
      2.1.2 на половину полосы  
      2.1.3 на всю полосу  
  2.2 динамический тихоход  

3. Следование за объектом:  
  a) начало движения  
  b) в движении  
  c) остановка  
  d) остановка и начало движения(пробка)  

4. Проезд по тоннелю.  