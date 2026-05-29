# ZephyrOS Flatpaks

A curated Flatpak repository bringing lightweight system tools, utilities, and dashboards to ZephyrOS and other Fedora Atomic-style Linux distributions.

The repository is hosted at [https://repo.zephyros.buzz](https://repo.zephyros.buzz).

---

## 1. Enable the ZephyrOS Repository

To access the flatpaks, add the ZephyrOS Flatpak remote repository to your Linux system configuration by running the following command in your terminal:

```bash
flatpak remote-add --if-not-exists zephyros https://repo.zephyros.buzz/index.flatpakrepo
```

Alternatively, you can download and open the repository configuration file directly:

* [Add Repository (.flatpakrepo)](https://repo.zephyros.buzz/index.flatpakrepo)

---

## 2. Available Applications

### 🚀 ZephyrOS Hello

An elegant and lightweight welcome utility and system dashboard crafted for ZephyrOS, welcoming users and presenting system information in a beautiful user interface.

* **Application ID:** `buzz.zephyros.hello`
* **Installation Command:**
  ```bash
  flatpak install zephyros buzz.zephyros.hello
  ```
* **Source Code:** [ZephyrOSHello on GitHub](https://github.com/theronlindsay/ZephyrOSHello)

### 🌲 Tree Trimmer

A  native GTK4 & Libadwaita utility built with Python, designed for managing Fedora Atomic Workstation setups. Easily search, install, and remove layered RPM packages.

* **Application ID:** `buzz.zephyros.treetrimmer`
* **Installation Command:**
  ```bash
  flatpak install zephyros buzz.zephyros.treetrimmer
  ```
* **Source Code:** [TreeTrimmer on GitHub](https://github.com/theronlindsay/TreeTrimmer)

---

## 🛠️ Development & Packaging

To build and test these Flatpaks locally during development:

### Build ZephyrOS Hello

```bash
flatpak-builder --user --install --force-clean _flatpak_build buzz.zephyros.hello.json
```

### Build Tree Trimmer

```bash
flatpak-builder --user --install --force-clean _flatpak_build buzz.zephyros.treetrimmer.json
```

### Generate Static Repository Output

To compile a flatpak repository structure for hosting:

```bash
flatpak-builder --force-clean --repo=repo build-dir buzz.zephyros.hello.json
flatpak build-update-repo --generate-static-deltas repo
```
