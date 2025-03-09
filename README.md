__Структура проекта__
project
 ├──index.html
 ├──script.js 
 └──sytle.css

# Progress Block Component

Прототип блока Progress для использования в мобильных web-приложениях. Компонент предназначен для отображения процесса выполнения задач и их прогресса.

## Особенности

### Основной функционал
- Отображение прогресса в виде круговой диаграммы
- API для управления состоянием
- Легкая интеграция в другие приложения
- Адаптивный дизайн
- Масштабируемость интерфейса

### Состояния
1. **Normal**
   - Базовое состояние
   - Управление размером дуги через значение Value (0-100)
   - Начало дуги в позиции 12 часов
   - Движение по часовой стрелке

2. **Animated**
   - Вращение элемента по часовой стрелке
   - Настраиваемая скорость анимации

3. **Hidden**
   - Скрытие блока со страницы

## Технические характеристики

### Размеры
- Мобильная версия: 320x568 px
- Десктопная версия: 568x320 px

### Технологии
- Чистый JavaScript (без фреймворков)
- CSS (без препроцессоров)
- HTML (без шаблонизаторов)

## API

### Класс ProgressBlock

```javascript
const progress = new ProgressBlock(containerElement);
```

#### Методы
- `setValue(value)` - установка значения прогресса (0-100)
- `setAnimated(animated)` - управление анимацией
- `setHidden(hidden)` - управление видимостью
- `setAnimationSpeed(duration)` - установка скорости анимации
- `getValue()` - получение текущего значения
- `isAnimated()` - проверка состояния анимации
- `isHidden()` - проверка видимости

### Класс ScaleController

```javascript
const scaleController = new ScaleController();
```

#### Функционал
- Управление масштабом интерфейса (50-150%)
- Плавная анимация масштабирования
- Сохранение пропорций элементов

## Элементы управления

### Value Input
- Тип: number
- Диапазон: 0-100
- Формат: текстовое поле

### Animate Toggle
- Тип: checkbox
- Состояния: on/off
- Стиль: переключатель

### Hide Toggle
- Тип: checkbox
- Состояния: on/off
- Стиль: переключатель

### Scale Control
- Тип: number
- Диапазон: 50-150
- Шаг: 25
- Расположение: левый верхний угол

## Адаптивность

### Мобильная версия
- Вертикальное расположение элементов
- Прогресс-бар сверху
- Элементы управления снизу

### Десктопная версия
- Горизонтальное расположение
- Прогресс-бар слева
- Элементы управления справа

## Установка и использование

1. Подключите файлы:
```html
<link rel="stylesheet" href="style.css">
<script src="script.js"></script>
```

2. Добавьте HTML структуру:
```html
<div class="container">
  <div class="progress-block-container">
    <!-- Progress Block Structure -->
  </div>
  <div class="controls">
    <!-- Controls Structure -->
  </div>
</div>
```

3. Инициализируйте компонент:
```javascript
const progressBlock = new ProgressBlock(containerElement);
```

## Пример использования

```javascript
// Создание экземпляра
const progress = new ProgressBlock(document.querySelector('.progress-block-container'));

// Установка значения
progress.setValue(75);

// Включение анимации
progress.setAnimated(true);

// Установка скорости анимации
progress.setAnimationSpeed(3);
```

## Совместимость
- Современные браузеры (Chrome, Firefox, Safari, Edge)
- Мобильные браузеры
- Адаптивность под различные устройства и ориентации экрана