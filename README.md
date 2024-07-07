<div align="center">
  <h1 align="center">Udomatic Fedora Customization</h1>
  <p align="center">A user oriented customization for Fedora</p>
</div>

## 0. Prerequistis
### Git Commands
You'll need certain fonts and themes before starting to customize your Fedora GNOME environment.
```bash
git clone https://github.com/sahibjotsaggu/San-Francisco-Pro-Fonts
git clone https://github.com/vinceliuice/WhiteSur-gtk-theme
git clone https://github.com/vinceliuice/WhiteSur-icon-theme
git clone https://github.com/powerline/fonts/blob/master/Meslo%20Dotted/Meslo%20LG%20L%20DZ%20Regular%20for%20Powerline.ttf
```
### Extensions
For other customizations to work, you'll need a way to install extensions, which could be easily done through the extension manager:

<a href="https://flathub.org/apps/details/com.mattjakeman.ExtensionManager">
<img src="https://flathub.org/assets/badges/flathub-badge-i-en.png" width="190px" />
</a>

Required extensions:
-   [Blur My Shell](https://extensions.gnome.org/extension/3193/blur-my-shell/)
    
-   [Customize Clock on Lock Screen](https://extensions.gnome.org/extension/4663/customize-clock-on-lock-screen/)
    
-   [Date Menu Formatter](https://extensions.gnome.org/extension/4655/date-menu-formatter/)
## ⬇️ Installing the theme 
    

-   Make sure that user themes within the extension manager has been installed and enabled
-   Make sure to that whitesur has been cloned from github
-   Go into the whitesur folder, right click, and click run in terminal
-   Enter the command “./install.sh”
-   Repeat the two steps above, where instead of the whitesur theme folder, you go into the whitesur icon folder
-   Go into Tweaks
-   Click on Apperence
-   And Select whitesur-dark or any other of your preference

OR

Copy and Paste this command:
```bash
git clone https://github.com/vinceliuice/WhiteSur-gtk-theme/ ; git clone https://github.com/vinceliuice/WhiteSur-icon-theme ; git clone https://github.com/vinceliuice/WhiteSur-kde ; git clone https://github.com/vinceliuice/WhiteSur-cursors ; mkdir ~/.themes

cd ./WhiteSur-gtk-theme ; ./install.sh -m -l -b default ; sudo ./install.sh -m -l -b default ; ./tweaks -F -s ; ./tweaks --dash-to-dock -c dark ; sudo ./tweaks.sh --gdm --color Dark --opacity solid --no-darken --no-blur -b default ; cd ../WhiteSur-kde ; ./install.sh ; sudo ./install.sh ; cd ../WhiteSur-icon-theme/ ; ./install.sh ; sudo ./install.sh ; cd ../WhiteSur-cursors/ ; ./install.sh ; sudo ./install.sh
```
  

  

### 🇦 Font Customization
    

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXeYHvTCcfvC7BoMM1sr8dKpNRP4Dc7OiIu0euYuqu3FWWtfLUJD_NrtPmCLnqOfntcKa4AZvVyfsUqDQ_AKHHlEdau4y1xOZcryETC5HE2pS9LhmslTDU7kt4Z1kOkNq9uEGejKJ4IgKU_pjhm6NBSM7Wd2?key=-2JpPdW9JzM1a4hQug_BWQ)

-   Make sure San Franciso and Meslo Fonts has been cloned
-   On home create a folder and name it “.fonts”
-   Drag all the font files into the folder
-   Select each font into the the text above
-   Interface Text set to SF Pro Text Regular
-   Document Text set to SF Pro Text Regular
-   Monospace Text set to Meslo LG L DZ for Powerline Regular
-   Legacy Windows Titles set to SF Pro Text Bold
    

## 🛳️ Dock Customization
-   Go to ~/.local/share/gnome-shell/extensions/dash-to-dock
-   Edit stylesheet.css
-   Within this codeblock, change the margin to 0px
    
```bash
#dashtodockContainer.bottom.fixed #dash .dash-background {
	margin-top: 0px;
}
```
-   To change the width, modify the padding-top in the first code block and the padding-bottom in the second code block:
```bash
#dashtodockContainer.bottom.fixed #dash .dash-item-container .app-well-app,
#dashtodockContainer.bottom.fixed #dash .dash-item-container .show-apps {
	padding-top: 8px; }
#dashtodockContainer.bottom #dash .dash-item-container .app-well-app,
#dashtodockContainer.bottom #dash .dash-item-container .show-apps {
	padding: 2px 2px;
	padding-bottom: 10px;
	padding-top: 10px; }
```
## 🕒 Time Customization
-   Install Just Perfection and Date Menu Formatterin the Extension Manager
-   Navigate to Customize
-   Clock Menu Position: Right
-   Clock Menu Position Offset: 9
-   On Data Manu Formatter click on settings
-   Use the “EEE MMM d h:mm aaa” format without the quotations
-   To reduce the padding of the time, go into your respective theme
-   Click on the gnome-shell folder
-   Click on gnome-shell.css
-   Change the code block to these values:
```bash
#panel .panel-button.clock-display .clock {
	border: none;
	border-radius: 6px;
	background-color: transparent;
	box-shadow: none;
	padding: 0 0px !important;
	margin: 0 !important;
}
```
## 📢 Branding Customization
-   In Fedora, go to /usr/share/pixmaps
-   Replace each of the logo with your respective logos.
-   If you want to change the boot logo, go to /usr/share/plymouth/themes/
-   Check which theme is select by the command plymouth-set-default-theme
-   And check the list of themes you can choose from with plymouth-set-default-theme --list
## 🛸 Extra Extensions
-   You can install the blur-my-shell extension for a visually appearing shell closer resembling MacOS
-   You can also install Customize Clock on Lockscreen to make your clock say anything.
## 🔴 Color Issues
-    If certain apps do not display the color color scheme, make sure to first:
### Turn off high contrast mode
-   Accessibility Options > High Contrast = Off
### Make sure the settings.ini file has the GTK prefer dark theme is set to 1
-   ~/.config/gtk-4.0/settings.ini
-   Change from gtk-application-prefer-dark-theme=0 to gtk-application-prefer-dark-theme=1
## 🔧 Unrelated Issues
-   If certain YouTubes videos do not load, and displays an error, make sure to reinstall your codecs:
```bash
sudo dnf remove libswscale-free libavcodec-free
sudo dnf install ffmpeg ffmpeg-libs
```
