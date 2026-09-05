# 🌌 Kavo UI Library

Простая и удобная UI-библиотека для Roblox с современным интерфейсом и готовыми элементами управления.

## 📦 Подключение

```lua
local Kavo = loadstring(game:HttpGet("https://raw.githubusercontent.com/delivery-2347/w/refs/heads/main/super%20puper%20optimezison"))()
```
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^Тут она кастомная, потому что если вы будете что-то делать на оригинальной, она будет очень лагать. Если вы будете делать большие какие-то проекты, то библиотека, ну, будет лагать сильно. Вот эта версия, она более оптимизированней
## 🚀 Создание окна

```lua
local Window = Kavo.CreateLib("My Script", "RJTheme1")
```

Первый параметр — название окна.

Второй — тема оформления.

## 🎨 Темы

В библиотеке доступны:

```text
RJTheme1
RJTheme2
RJTheme3
RJTheme4
RJTheme5
RJTheme6
RJTheme7
RJTheme8
```

Например:

```lua
local Window = Kavo.CreateLib("My Script", "RJTheme4")
```

---

# 📁 Tabs и Sections

### Создание вкладки

```lua
local Tab = Window:NewTab("Main")
```

### Создание секции

```lua
local Section = Tab:NewSection("Settings")
```

После этого в секцию можно добавлять элементы.

---

# 🔘 Button

Создание кнопки:

```lua
Section:NewButton("Click Me", "Описание кнопки", function()
    print("Button clicked!")
end)
```

При нажатии выполняется функция.

### Изменение названия

Кнопка возвращает объект, который можно использовать для изменения:

```lua
local Button = Section:NewButton("Click Me", "Описание", function()
    print("Hello")
end)

Button:UpdateButton("New Name")
```

---

# 🔄 Toggle

```lua
Section:NewToggle("Enabled", "Включение функции", function(state)
    print(state)
end)
```

`state` будет:

```lua
true
```

или

```lua
false
```

### Изменение значения

```lua
local Toggle = Section:NewToggle("Enabled", "Описание", function(state)
    print(state)
end)

Toggle:UpdateToggle(true)
```

### Изменение названия

Название можно изменить через параметры обновления toggle.

---

# 🎚️ Slider

```lua
Section:NewSlider("Speed", "Скорость", 100, 0, function(value)
    print(value)
end)
```

Здесь:

```text
100 = максимальное значение
0   = минимальное значение
```

При изменении slider в callback передаётся новое значение.

---

# 📝 TextBox

```lua
Section:NewTextBox("Username", "Введите текст", function(text)
    print(text)
end)
```

После ввода текста он передаётся в callback.

---

# 📋 Dropdown

```lua
Section:NewDropdown(
    "Mode",
    "Выберите режим",
    {"Normal", "Fast", "Slow"},
    function(value)
        print(value)
    end
)
```

При выборе элемента callback получает выбранное значение.

---

# ⌨️ Keybind

```lua
Section:NewKeybind(
    "Toggle UI",
    "Клавиша для переключения",
    Enum.KeyCode.RightShift,
    function(key)
        print(key)
    end
)
```

Пользователь может изменить клавишу прямо через интерфейс.

---

# 🌈 Color Picker

```lua
Section:NewColorPicker(
    "Color",
    "Выберите цвет",
    Color3.fromRGB(255, 0, 0),
    function(color)
        print(color)
    end
)
```

Callback получает выбранный `Color3`.

---

# 🖥️ Управление интерфейсом

Скрыть или показать интерфейс:

```lua
Kavo:ToggleUI()
```

Каждый вызов переключает состояние интерфейса.

---

# 🎨 Изменение цвета

Цвета интерфейса можно менять во время работы:

```lua
Kavo:ChangeColor("SchemeColor", Color3.fromRGB(255, 0, 0))
```

Доступные основные параметры:

```text
SchemeColor
Background
Header
TextColor
ElementColor
```

Например:

```lua
Kavo:ChangeColor(
    "ElementColor",
    Color3.fromRGB(40, 40, 40)
)
```

---

# 📌 Полный пример

```lua
local Kavo = loadstring(game:HttpGet(
    "https://raw.githubusercontent.com/delivery-2347/w/refs/heads/main/super%20puper%20optimezison"
))()

local Window = Kavo.CreateLib("My Script", "RJTheme1")

local Main = Window:NewTab("Main")
local Section = Main:NewSection("Settings")

Section:NewButton("Hello", "Нажми на кнопку", function()
    print("Hello!")
end)

Section:NewToggle("Enabled", "Включить функцию", function(state)
    print("Enabled:", state)
end)

Section:NewSlider("Speed", "Настройка скорости", 100, 0, function(value)
    print("Speed:", value)
end)

Section:NewTextBox("Text", "Введите текст", function(text)
    print("Text:", text)
end)

Section:NewDropdown(
    "Mode",
    "Выберите режим",
    {"Normal", "Fast", "Slow"},
    function(value)
        print("Mode:", value)
    end
)

Section:NewKeybind(
    "Keybind",
    "Выберите клавишу",
    Enum.KeyCode.RightShift,
    function(key)
        print("Key:", key)
    end
)

Section:NewColorPicker(
    "Color",
    "Выберите цвет",
    Color3.fromRGB(255, 0, 0),
    function(color)
        print("Color:", color)
    end
)
```
