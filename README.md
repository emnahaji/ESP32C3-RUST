
# 🚀 Guide de démarrage : Projet Rust sur ESP32

Ce README explique étape par étape comment vérifier votre environnement et créer un projet Rust pour ESP32 (ESP-IDF / esp-rs).

---

# 1️⃣ Vérification de l’environnement

Avant de commencer, assurez-vous que tout est bien installé.

## 🔧 Vérifier Rust

```bash
rustc -V
cargo -V
```

👉 Vous devez voir une version de Rust et Cargo.

---

## 🔧 Vérifier le toolchain ESP (esp-rs)

```bash
rustup show
```

---

## 🔧 Vérifier ESP-IDF (si utilisé)

```bash
idf.py --version
```

---

## 🔧 Vérifier Python (important pour ESP-IDF)

```bash
python --version
```

---

## 🔧 Vérifier Git

```bash
git --version
```

---

# 2️⃣ Installer le support ESP32 pour Rust

## Installer le target ESP32-C3 (exemple)

```bash
rustup target add riscv32imc-unknown-none-elf
```

## Installer cargo-espflash (flash firmware)

```bash
cargo install espflash
```

## Installer cargo-generate (création projet)

```bash
cargo install cargo-generate
```

---

# 3️⃣ Création du projet Rust ESP32

## Créer un projet avec template officiel

```bash
cargo generate esp-rs/esp-idf-template
```

👉 Choisir :

* ESP32-C3 (ou votre chip)
* WiFi / no_std selon besoin

---

# 4️⃣ Entrer dans le projet

```bash
cd nom_du_projet
```

---

# 5️⃣ Compiler le projet

```bash
cargo build
```

ou pour ESP-IDF :

```bash
cargo build --release
```

---

# 6️⃣ Flasher sur ESP32

## Méthode simple (espflash)

```bash
espflash flash target/riscv32imc-unknown-none-elf/release/nom_du_projet
```

## Avec port COM (Windows)

```bash
espflash flash COM3 target/riscv32imc-unknown-none-elf/release/nom_du_projet
```

---

# 7️⃣ Monitor (voir logs)

```bash
espflash monitor
```

---

# 8️⃣ Commandes utiles projet

## Nettoyer projet

```bash
cargo clean
```

## Rebuild complet

```bash
cargo build --release
```

## Mettre à jour dépendances

```bash
cargo update
```

---

# 🧠 Conseils importants

* Toujours vérifier le port USB avant flash
* Utiliser `release` pour test réel ESP32
* Garder ESP-IDF compatible avec version Rust

---

# 📌 Résumé rapide

```bash
rustc -V
cargo -V
cargo generate esp-rs/esp-idf-template
cargo build
espflash flash
espflash monitor
```

---

# ✨ Fin

Tu peux maintenant créer et flasher un projet Rust sur ESP32 🚀
