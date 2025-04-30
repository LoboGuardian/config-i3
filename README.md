# config-i3: Enhanced i3wm Configuration with Picom and Polybar

[![Maintenance](https://img.shields.io/maintenance/yes/2025)](https://github.com/your-username/config-i3/graphs/commit-activity)
[![License](https://img.shields.io/github/license/LoboGuardian/config-i3)](https://github.com/your-username/config-i3/blob/main/LICENSE)
![Arch Linux](https://img.shields.io/badge/Arch%20Linux-00BCD4?style=for-the-badge&logo=arch-linux&logoColor=fff)
![i3wm](https://img.shields.io/badge/i3wm-%234c7bf3.svg?style=for-the-badge&logo=i3&logoColor=fff)
![Picom](https://img.shields.io/badge/Picom-5A5A5A?style=for-the-badge&logo=linux&logoColor=fff)
![Polybar](https://img.shields.io/badge/Polybar-%23F0C674.svg?style=for-the-badge&logo=polybar&logoColor=black)

**Elevate your i3 window manager experience with this curated collection of configuration files for Picom and Polybar, complemented by custom, insightful scripts.**

This repository provides a comprehensive set of configurations designed to enhance the aesthetics and functionality of your i3 desktop environment. It includes a carefully crafted Picom configuration for visual improvements and a feature-rich Polybar setup with custom scripts to keep you informed and productive.

## ✨ Key Features

* **Visually Appealing with Picom:** Includes a `picom.conf` configured for smooth animations, elegant shadows, subtle fading effects, and adjustable window opacity.
* **Informative and Customizable Polybar:** Contains a `polybar` directory with:
    * A `config` file offering a thoughtfully designed status bar with a refined color scheme, modular structure, and clean layout.
    * A `config.bak` file, which is a backup of the previous Polybar configuration for safe experimentation.
    * A `launch.sh` script that intelligently handles launching Polybar on single or multiple monitor setups.
    * A `scripts` directory housing custom scripts for enhanced functionality.
* **Insightful Custom Scripts:** Located within the `polybar/scripts/` directory, these scripts provide valuable information directly on your Polybar:
    * `arch_updates.sh`: Stay up-to-date by displaying the number of pending system updates (specifically for Arch-based distributions).
    * `info-eyestrain.sh`: Promotes healthy habits by providing timely reminders to take breaks and reduce eye strain.
    * `info-hackspeed.sh`: Track your typing proficiency with a real-time display of your words per minute (WPM).
    * `network-traffic.sh`: Monitor your network usage with live upload and download speeds.
    * `weather-openmap.sh`: Get at-a-glance weather updates powered by the OpenWeatherMap API.

## 🛠️ Installation and Usage

Follow these steps to integrate these configurations into your i3 setup:

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/LoboGuardian/config-i3.git ~/.config/config-i3
    ```

2.  **Install Dependencies:** Ensure you have the following packages installed on your system:
    * **Picom:** The compositor providing visual effects. Installation command varies by distribution (e.g., `sudo pacman -S picom` on Arch, `sudo apt install picom` on Debian/Ubuntu).
    * **Polybar:** The flexible and feature-rich status bar. Install using your distribution's package manager (e.g., `sudo pacman -S polybar`, `sudo apt install polybar`).
    * **OpenWeatherMap API Key:** Required for the `polybar/scripts/weather-openmap.sh` script. Sign up for a free API key at [https://openweathermap.org/api](https://openweathermap.org/api).
    * **`curl`:** A command-line tool for transferring data with URLs (usually pre-installed).
    * **`xprintidle`:** Utility to query the last user input idle time (required for `polybar/scripts/info-eyestrain.sh`). Install via your package manager (e.g., `sudo pacman -S xprintidle`, `sudo apt install xprintidle`).
    * **`wtype`:** A utility to type keystrokes (required for `polybar/scripts/info-hackspeed.sh`). Install via your package manager (e.g., `sudo pacman -S wtype`, `sudo apt install wtype`).

3.  **Configure Picom:**
    * Create the Picom configuration directory if it doesn't exist:
        ```bash
        mkdir -p ~/.config/picom
        ```
    * Copy the provided `picom.conf`:
        ```bash
        cp ~/.config/config-i3/picom.conf ~/.config/picom/picom.conf
        ```
    * To automatically start Picom with i3, add the following line to your i3 configuration file (`~/.config/i3/config`):
        ```
        exec --no-startup-id picom --config ~/.config/picom/picom.conf
        ```

4.  **Configure Polybar:**
    * Copy the `polybar` directory to your `~/.config/` directory:
        ```bash
        cp -r ~/.config/config-i3/polybar ~/.config/
        ```
    * **Make the scripts executable:**
        ```bash
        chmod +x ~/.config/polybar/scripts/*
        ```
    * **Set OpenWeatherMap API Key:** Open `~/.config/polybar/scripts/weather-openmap.sh` and replace `YOUR_OPENWEATHERMAP_API_KEY` with your actual API key. You can also customize the `CITY_ID` and other parameters within the script.
    * To automatically start Polybar with i3, add the following line to your i3 configuration file (`~/.config/i3/config`):
        ```
        exec --no-startup-id ~/.config/polybar/launch.sh
        ```

5.  **Restart i3:**
    Reload your i3 configuration by pressing `$mod + Shift + r` (where `$mod` is typically the Windows or Alt key). This will apply the new Picom and Polybar configurations.

## ⚙️ Customization

Personalize these configurations to perfectly match your workflow and aesthetic preferences:

* **Picom:** Dive into `~/.config/picom/picom.conf` to fine-tune animation durations, shadow properties, fading behavior, and inactive window opacity. Refer to the Picom documentation for a comprehensive list of available options.
* **Polybar:** Edit `~/.config/polybar/config` to adjust the color scheme, add or remove modules, modify the layout, and customize the behavior of existing modules. The Polybar wiki is an excellent resource for exploring its extensive configuration possibilities.
* **Scripts:** Feel free to modify the existing scripts in `~/.config/polybar/scripts/` or create your own to display information that is most relevant to you. Remember to update the `~/.config/polybar/config` to incorporate any new custom modules.

## 📄 License

This project is licensed under the [MIT License](LICENSE).

## ❤️ Acknowledgements

A big thank you to the developers of i3, Picom, and Polybar for creating such powerful and customizable tools!

Enjoy your enhanced i3 desktop environment!