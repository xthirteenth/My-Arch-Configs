# 🐧 My Arch Configs

[![Arch Linux](https://img.shields.io/badge/Arch%20Linux-1793D1?style=for-the-badge&logo=arch-linux&logoColor=white)](https://archlinux.org/)
[![Hyprland](https://img.shields.io/badge/Hyprland-58E1FF?style=for-the-badge&logo=wayland&logoColor=black)](https://hyprland.org/)
[![DWM](https://img.shields.io/badge/DWM-1177AA?style=for-the-badge&logo=dwm&logoColor=white)](https://dwm.suckless.org/)
[![License](https://img.shields.io/badge/License-Custom-red?style=for-the-badge)](LICENSE)
[![Development](https://img.shields.io/badge/Status-In%20Development-yellow?style=for-the-badge)](https://github.com/your-username/My-Arch-Configs)

> 💎 **Продвинутые конфигурации Arch Linux от skreamer (mvko)**  
> Полнофункциональная система с Wayland/X11, оптимизированная для производительности и удобства

## ⚠️ **ВАЖНОЕ ПРЕДУПРЕЖДЕНИЕ**

> 🚧 **Данные конфигурации находятся в стадии активной разработки и тестирования!**
>
> - ❌ **НЕ рекомендуется** для использования в производственных системах
> - 🔧 **Требует доработки** и настройки под конкретное оборудование
> - 🐛 **Может содержать ошибки** и несовместимости
> - 💥 **Использование на свой страх и риск** - автор не несёт ответственности за возможные повреждения системы
> - 📋 **Обязательно делайте резервные копии** перед применением конфигураций

## 📋 Обзор системы

| Компонент               | Значение           |
| ----------------------- | ------------------ |
| 🏗️ **Дистрибутив**      | Arch Linux         |
| 🪟 **WM (основной)**    | Hyprland (Wayland) |
| 🔧 **Init система**     | systemd            |
| 🗂️ **Файловая система** | btrfs              |
| 🔊 **Аудиосистема**     | PulseAudio         |
| 🖥️ **Display сервер**   | Wayland + XWayland |
| 🐚 **Shell**            | Zsh + плагины      |

## 🚀 Особенности

### 🎨 **Окружение рабочего стола**

- **Hyprland** - современный композитор Wayland с анимациями и эффектами
- **Waybar** - настраиваемая панель для Wayland
- **SwayNC** - центр уведомлений
- **Rofi** - лаунчер приложений

### 🛠️ **Инструменты разработки**

- **VSCode** с темой Absolute Black
- **Neovim** - продвинутый текстовый редактор
- **Docker** + Docker Compose
- **Git** с автодополнением и подсветкой
- **Kitty** терминал

### 📦 **Менеджер пакетов**

- Официальные репозитории Arch Linux
- AUR (Arch User Repository) для дополнительных пакетов
- Оптимизированные списки пакетов

## 📁 Структура проекта

```
My-Arch-Configs/
├── 🔤 fonts/                   # JetBrains Mono Nerd Font
├── 🎨 icons/                   # Иконки и скриншоты
├── 🐚 zsh-syntax-highlighting/ # Подсветка синтаксиса Zsh
├── ⚙️ etc/                     # Системные конфигурации
│   └── modprobe.d/            # Модули ядра
├── 📋 *.packages              # Списки пакетов
├── 🔧 usr/share/applications/ # Desktop файлы
└── 🐚 zsh                     # Конфигурация Zsh
```

## 🛠️ Установка

### 📋 Предварительные требования

- Установленная базовая система Arch Linux
- Доступ root или sudo
- Активное интернет-соединение
- Настроенный AUR helper (yay, paru)

### 🚀 Быстрая установка

> ⚠️ **Перед началом установки:**
>
> - Сделайте полную резервную копию системы
> - Убедитесь, что у вас есть способ восстановления системы
> - Тестируйте на виртуальной машине перед установкой на основную систему

```bash
# Клонируем репозиторий
git clone https://github.com/your-username/My-Arch-Configs.git
cd My-Arch-Configs

# Устанавливаем AUR helper (если не установлен)
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
cd ..

# Обновляем систему
sudo pacman -Syu

# Устанавливаем основные пакеты
sudo pacman -S --needed base-devel git curl wget

# Устанавливаем пакеты для разработки
sudo pacman -S --needed code neovim docker docker-compose

# Устанавливаем зависимости для Wayland
sudo pacman -S --needed wayland xorg-xwayland

# Устанавливаем Hyprland (если нужен)
sudo pacman -S hyprland waybar swaync rofi-wayland

# Копируем шрифты
mkdir -p ~/.local/share/fonts
cp -r fonts/* ~/.local/share/fonts/
fc-cache -fv

# Настраиваем Zsh
cp -r zsh-syntax-highlighting ~/.config/
echo 'source ~/.config/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh' >> ~/.zshrc

# Устанавливаем дополнительные пакеты из AUR
yay -S --needed kitty-git # или kitty

# Копируем конфигурации системы (осторожно!)
sudo cp -r etc/* /etc/

# Копируем desktop файлы
sudo cp -r usr/share/applications/* /usr/share/applications/
```

### 🎨 Установка Hyprland

```bash
# Устанавливаем Hyprland и дополнения
sudo pacman -S hyprland waybar swaync rofi-wayland

# Создаем директории для конфигураций
mkdir -p ~/.config/{hypr,waybar,swaync}

# Копируем конфигурации (создайте их отдельно)
# cp config/hypr/* ~/.config/hypr/
# cp config/waybar/* ~/.config/waybar/
# cp config/swaync/* ~/.config/swaync/
```

## 📊 Мониторинг системы

В проекте включены инструменты для мониторинга:

```bash
# Устанавливаем мониторинг
sudo pacman -S htop dust fastfetch

# Дополнительные инструменты
yay -S btop # современная замена htop
```

## 🔧 Дополнительные компоненты

### 📱 Приложения

- **Firefox** - веб-браузер
- **Telegram Desktop** - мессенджер
- **Ranger** - файловый менеджер
- **VSCode** - редактор кода

### 🔊 Аудио

- **PulseAudio** - совместимость
- **pavucontrol** - графический микшер
- **pamixer** - CLI микшер

```bash
# Установка аудио
sudo pacman -S pavucontrol pamixer
```

### 🖼️ Графика и медиа

- **Mesa** - OpenGL драйверы
- **Hyprpaper** - обои для Wayland
- **grim + slurp** - скриншоты

```bash
# Установка графических утилит
sudo pacman -S mesa grim slurp
yay -S hyprpaper-git
```

## 🚧 Статус разработки

### 📊 Текущее состояние

| Компонент                | Статус          | Описание                                       |
| ------------------------ | --------------- | ---------------------------------------------- |
| 🔤 **Шрифты**            | 🟢 Готово       | Полный набор JetBrains Mono                    |
| 🪟 **DWM setup**         | 🟢 Стабильно    | Проверено на нескольких системах               |
| 🎨 **Hyprland config**   | 🔴 В разработке | Базовая конфигурация, много TODO               |
| 📦 **Списки пакетов**    | 🟡 Частично     | Основные пакеты, может не хватать зависимостей |
| 🐚 **Zsh настройки**     | 🟡 Базовые      | Только подсветка синтаксиса                    |
| ⚙️ **Системные конфиги** | 🟡 Тестирование | Модули ядра и системные файлы                  |

### 🔄 Планы развития

- [ ] Добавить полные конфигурации Hyprland
- [ ] Создать скрипты автоматической установки
- [ ] Добавить конфигурации для различных DE
- [ ] Расширить документацию
- [ ] Создать Docker образы для тестирования
- [ ] Добавить CI/CD для проверки конфигураций
- [ ] Создать PKGBUILD файлы для простой установки

### 🧪 Тестирование

Конфигурации тестируются на:

- **Основная система:** Arch Linux с systemd
- **Виртуальные машины:** VirtualBox, QEMU
- **Железо:** AMD Ryzen, Intel Core i-series

**Не тестировалось на:**

- ARM архитектуре
- Экзотическом оборудовании
- Старых версиях Arch Linux

## 🐛 Решение проблем

### 🔧 Распространенные проблемы

**Проблемы с установкой пакетов:**

```bash
# Обновить базы данных пакетов
sudo pacman -Sy

# Очистить кэш пакетов
sudo pacman -Sc

# Переустановить поврежденный пакет
sudo pacman -S --reinstall package-name

# Проверить зависимости
pacman -Qi package-name
```

**Проблемы с AUR:**

```bash
# Обновить AUR helper
yay -Syu

# Очистить кэш AUR
yay -Sc

# Переустановить AUR пакет
yay -S --reinstall package-name
```

**Проблемы с Wayland:**

```bash
# Проверить переменные окружения
echo $XDG_SESSION_TYPE
echo $WAYLAND_DISPLAY

# Установить недостающие компоненты
sudo pacman -S xorg-xwayland
```

**Проблемы с шрифтами:**

```bash
# Обновить кэш шрифтов
fc-cache -fv

# Проверить установленные шрифты
fc-list | grep -i jetbrains
```

### ⚠️ Критические предупреждения

- **Не копируйте системные конфигурации** без проверки совместимости
- **Делайте резервные копии** перед большими изменениями
- **Тестируйте на виртуалках** перед применением на основной системе
- **Проверяйте зависимости** перед установкой пакетов

## 🤝 Участие в разработке

1. Fork репозитория
2. Создайте feature branch (`git checkout -b feature/amazing-feature`)
3. Commit изменения (`git commit -m 'Add amazing feature'`)
4. Push в branch (`git push origin feature/amazing-feature`)
5. Создайте Pull Request

## 📜 Лицензия

Этот проект распространяется под **кастомной лицензией** с следующими условиями:

- ✅ **Разрешено:** Личное использование, изучение, модификация, распространение
- ❌ **Запрещено:** Коммерческое использование без разрешения
- 🔒 **Требования:** Все производные работы должны быть открытыми
- 🛡️ **Защита:** Встроенная защита от патентных претензий

**Для коммерческого использования требуется письменное разрешение автора.**

См. файл [`LICENSE`](LICENSE) для полного текста лицензии.

## 📞 Контакты

- **Автор:** skreamer (mvko)
- **GitHub:** [your-profile](https://github.com/your-username)

---

<div align="center">

**⭐ Понравился проект? Поставьте звездочку! ⭐**

_Создано с ❤️ для сообщества Arch Linux_

</div>
