На этой странице перечислены все поддерживаемые способы загрузки и установки Obsidian.

## Установка Obsidian в Windows

1. Откройте браузер и перейдите по ссылке [Download Obsidian](https://obsidian.md/download).
2. Напротив **Windows** нажмите на **Standard (64-bit)**, чтобы скачать установочный файл.
3. Откройте установочный файл и следуйте инструкциям.
4. Откройте Obsidian так же, как и любое другое приложение.

## Установка Obsidian в macOS

1. Откройте браузер и перейдите по ссылке [Download Obsidian](https://obsidian.md/download).
2. Напротив **macOS** нажмите на **Universal (Silicone and Intel)**, чтобы скачать установочный файл.
3. Откройте установочный файл.
4. В открывшемся окне перетащите Obsidian в папку Applications.
5. Откройте Obsidian так же, как и любое другое приложение.

## Установка Obsidian в Linux

Если вы используете Linux, вы можете установить Obsidian несколькими способами. Следуйте инструкциям для используемой вами системы управления пакетами.

### Установка с помощью Snap

1. Откройте браузер и перейдите по ссылке [Download Obsidian](https://obsidian.md/download).
2. Напротив **Linux** нажмите на **Snap**, чтобы скачать установочный файл.
3. Откройте терминал и перейдите в папку, в которую вы загрузили установочный файл.
4. В терминале выполните следующую команду для установки Snap-пакета: (флаг `--dangerous` необходим, поскольку компания Canonical, создавшая Snap, не проверила наш пакет; флаг `--classic` позволяет Obsidian получить доступ за пределы песочницы, где хранятся ваши заметки).

   ```bash
   snap install obsidian_<version>_<arch>.snap --dangerous --classic
   ```

5. Откройте Obsidian так же, как и любое другое приложение.

### Установка с помощью AppImage

1. Откройте браузер и перейдите по ссылке [Download Obsidian](https://obsidian.md/download).
2. Напротив **Linux** нажмите на **AppImage**, чтобы скачать установочный файл.
3. Откройте терминал и перейдите в папку, в которую вы загрузили установочный файл.
4. В терминале выполните следующую команду для открытия Obsidian:

   ```bash
   chmod u+x Obsidian-<version>.AppImage
   ./Obsidian-<version>.AppImage
   ```

### Установка с помощью Flatpak

1. In your terminal, run the following command to install Obsidian:

   ```bash
   flatpak install flathub md.obsidian.Obsidian
   ```

2. Open Obsidian by running the following command:

   ```bash
   flatpak run md.obsidian.Obsidian
   ```

## Установка Obsidian в Android

1. Find Obsidian on the [Play Store](https://play.google.com/store/apps/details?id=md.obsidian).
2. Tap **Install** to download the app.
3. Open Obsidian the same way you would open any other app.

## Установка Obsidian в iPhone и iPad

1. Find Obsidian on the [App Store](https://apps.apple.com/us/app/obsidian-connected-notes/id1557175442).
2. Tap **Get** to download the app.
3. Open Obsidian the same way you would open any other app.
