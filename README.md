[README.md](https://github.com/user-attachments/files/32332413/README.md)
# Kanagawa-ult-dots

Мои dotfiles для **Hyprland** в стиле **Kanagawa**.

## Содержимое

``` text
.
├── fuzzel/
│   └── fuzzel.ini
├── hypr stuff/
│   ├── hyprland.conf
│   └── hyprlock.conf
└── waybar/
    ├── config
    └── style.css
```

## Зависимости

Основные программы:

-   Hyprland
-   Hyprlock
-   Waybar
-   Fuzzel
-   Foot
-   Dolphin
-   Swww
-   Hypridle
-   Mako
-   Wlogout
-   Waypaper
-   Grimblast
-   Pavucontrol

Шрифт:

-   JetBrainsMono Nerd Font

Для иконок:

-   Papirus

> Конфигурация содержит настройки для NVIDIA. Если у тебя AMD/Intel,
> убери NVIDIA-переменные из `hyprland.conf` и модуль `custom/gpu` из
> Waybar.

## Установка

### 1. Клонирование

``` bash
git clone https://github.com/ultifirnen/Kanagawa-ult-dots.git
cd Kanagawa-ult-dots
```

### 2. Сделай резервную копию

Перед заменой конфигов рекомендуется сохранить свои текущие настройки:

``` bash
cp -r ~/.config/hypr ~/.config/hypr.backup 2>/dev/null
cp -r ~/.config/waybar ~/.config/waybar.backup 2>/dev/null
cp -r ~/.config/fuzzel ~/.config/fuzzel.backup 2>/dev/null
```

### 3. Установи конфиги

Создай необходимые директории:

``` bash
mkdir -p ~/.config/hypr
mkdir -p ~/.config/waybar
mkdir -p ~/.config/fuzzel
```

Скопируй файлы:

``` bash
cp "hypr stuff/hyprland.conf" ~/.config/hypr/hyprland.conf
cp "hypr stuff/hyprlock.conf" ~/.config/hypr/hyprlock.conf
cp waybar/config ~/.config/waybar/config
cp waybar/style.css ~/.config/waybar/style.css
cp fuzzel/fuzzel.ini ~/.config/fuzzel/fuzzel.ini
```

### 4. Перезапусти приложения

Перезапусти Waybar:

``` bash
pkill waybar
waybar &
```

После этого лучше перелогиниться в Hyprland.

## Важные настройки

### NVIDIA

`hyprland.conf` содержит:

``` ini
env = LIBVA_DRIVER_NAME,nvidia
env = __GLX_VENDOR_LIBRARY_NAME,nvidia
env = NVD_BACKEND,direct
```

Если у тебя не NVIDIA, эти строки лучше удалить.

Waybar также получает загрузку GPU через:

``` bash
nvidia-smi
```

На системе без NVIDIA удали из `waybar/config` модуль `custom/gpu` и его
использование в `modules-right`.

### Active app

Waybar использует скрипт:

``` text
~/.config/waybar/scripts/active-app.sh
```

Сам скрипт не входит в этот репозиторий. Если его нет, удали
`custom/active-app` из `waybar/config` или добавь свой скрипт.

## Обновление

Если репозиторий уже был клонирован:

``` bash
cd ~/Kanagawa-ult-dots
git pull
```

После обновления снова скопируй изменившиеся конфиги в `~/.config`.

## Примечание

Это мои личные dotfiles, поэтому некоторые настройки могут требовать
адаптации под твоё железо, монитор и установленные программы.

Если что-то не работает --- сначала проверь зависимости и пути к
программам в `hyprland.conf` и `waybar/config`.
