# Guide to Installing and Using the AUR on Arch Linux

The **AUR** (*Arch User Repository*) is a community-maintained repository for Arch Linux where users share packages that are not available in the official repositories.  
It allows you to install software easily by automatically compiling it from source.

---

## 📌 1. Installing an AUR Helper (yay)

`yay` is one of the most popular helpers for managing AUR packages.  
It simplifies installation, updates, and removal of packages.

### Install yay manually:
```bash
# Update system packages
sudo pacman -Syu

# Install packages required for compilation (base-devel) and git
sudo pacman -S --needed base-devel git

# Clone yay repository
git clone https://aur.archlinux.org/yay.git

# Enter the directory
cd yay

# Build and install
makepkg -si
```

> **Note:** `base-devel` is essential for building AUR packages as it includes tools like `make`, `gcc`, and others.

---

## 📌 2. Using yay

### 🔍 Search for packages
```bash
yay -Ss package-name
# Example:
yay -Ss google-chrome
```
> Shows all packages related to the search term (from both official repositories and the AUR).

### 📥 Install packages
```bash
yay -S package-name
# Example:
yay -S google-chrome
```

### ♻️ Update packages
```bash
yay -Syu
```
> Updates all system packages **including** AUR packages.

### ❌ Remove packages
```bash
yay -Rns package-name
# Example:
yay -Rns google-chrome
```
> The `-Rns` flag removes the package and any dependencies not required by other programs.

### 🗑️ Clear cache
```bash
yay -Sc
```
> Removes old package versions stored in cache.

### 🧹 Remove orphan dependencies
```bash
sudo pacman -Rns $(pacman -Qdtq)
```
> Deletes packages installed as dependencies that are no longer needed.

---

## 📌 3. Tips and Best Practices

- Always read the **PKGBUILD** before installing something from the AUR:
```bash
yay -G package-name
cd package-name
nano PKGBUILD
```
- Avoid installing AUR packages without verifying their source and reading the comments on the package page.
- Keep your system updated regularly with:
```bash
yay -Syu
```
- Clean caches regularly to save disk space:
```bash
yay -Sc
```

---

## 📚 References
- [Official AUR Page](https://aur.archlinux.org/)
- [Arch Linux Documentation](https://wiki.archlinux.org/title/Arch_User_Repository)
- [yay GitHub Repository](https://github.com/Jguer/yay)

---

Made by: **Lucas Bellucci Almendra**  
_The Matrix Bunny_
