# Guia de Instalação e Uso do AUR no Arch Linux

O **AUR** (*Arch User Repository*) é um repositório mantido pela comunidade do Arch Linux, onde usuários compartilham pacotes que não estão nos repositórios oficiais.  
Ele permite instalar softwares de forma simples, compilando o código-fonte automaticamente.

---

## 📌 1. Instalando um Helper do AUR (yay)

O `yay` é um dos helpers mais populares para gerenciar pacotes do AUR.  
Ele simplifica a instalação, atualização e remoção de pacotes.

### Instalar o yay manualmente:
```bash
# Atualizar pacotes do sistema
sudo pacman -Syu

# Instalar pacotes necessários para compilar (base-devel) e o git
sudo pacman -S --needed base-devel git

# Clonar o repositório do yay
git clone https://aur.archlinux.org/yay.git

# Entrar no diretório
cd yay

# Compilar e instalar
makepkg -si
```

> **Observação:** O `base-devel` é essencial para compilar pacotes do AUR, pois contém ferramentas como `make`, `gcc` e outras.

---

## 📌 2. Usando o yay

### 🔍 Pesquisar pacotes
```bash
yay -Ss nome-do-pacote
# Exemplo:
yay -Ss google-chrome
```
> Mostra todos os pacotes relacionados ao termo pesquisado (tanto do repositório oficial quanto do AUR).

### 📥 Instalar pacotes
```bash
yay -S nome-do-pacote
# Exemplo:
yay -S google-chrome
```

### ♻️ Atualizar pacotes
```bash
yay -Syu
```
> Atualiza todos os pacotes do sistema **incluindo** os do AUR.

### ❌ Remover pacotes
```bash
yay -Rns nome-do-pacote
# Exemplo:
yay -Rns google-chrome
```
> O `-Rns` remove o pacote e as dependências que não estão sendo usadas por outros programas.

### 🗑️ Limpar cache
```bash
yay -Sc
```
> Remove versões antigas dos pacotes armazenadas em cache.

### 🧹 Remover dependências órfãs
```bash
sudo pacman -Rns $(pacman -Qdtq)
```
> Apaga pacotes instalados como dependência que não são mais necessários.

---

## 📌 3. Dicas e Boas Práticas

- Sempre leia o **PKGBUILD** antes de instalar algo do AUR:
```bash
yay -G nome-do-pacote
cd nome-do-pacote
nano PKGBUILD
```
- Evite instalar pacotes do AUR sem verificar a procedência e os comentários na página do pacote.
- Mantenha seu sistema sempre atualizado com:
```bash
yay -Syu
```
- Limpe caches regularmente para economizar espaço:
```bash
yay -Sc
```

---

## 📚 Referências
- [Página oficial do AUR](https://aur.archlinux.org/)
- [Documentação do Arch Linux](https://wiki.archlinux.org/title/Arch_User_Repository)
- [Repositório do yay no GitHub](https://github.com/Jguer/yay)

---

Feito por: **Lucas Bellucci Almendra**  
_The Matrix Bunny_
