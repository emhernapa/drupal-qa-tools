# Drupal QA Tools

Development tools for Drupal projects: PHPStan, PHPMD, PHPCS, and Drupal coding standards ready to use.

## 🧠 Description

This repository provides a ready-to-use configuration of static analysis tools and coding standards for Drupal 10 projects. It includes:

- **PHPStan** for static code analysis  
- **PHPMD** for detecting problematic code  
- **PHPCS** with Drupal coding standards  
- Predefined configuration files to facilitate integration  

Ideal for integrating as a development dependency in multiple Drupal projects via Composer.

---

## 📦 Installation

1. Add the repository to your `composer.json`:

```json
"repositories": {
    "drupal-qa-tools": {
        "type": "vcs",
        "url": "https://github.com/emhernapa/drupal-qa-tools"
    }
}
```

2. Add the following scripts to create the config files to your `composer.json`:

```json
"scripts": {
      "post-install-cmd": [
          "cp ./vendor/emhernapa/drupal-qa-tools/config/phpstan.neon phpstan.neon",
          "cp ./vendor/emhernapa/drupal-qa-tools/config/phpmd.xml phpmd.xml",
          "cp ./vendor/emhernapa/drupal-qa-tools/config/phpcs.xml phpcs.xml"
      ]
  }
```

3. Require it as a development dependency:

```bash
composer require emhernapa/drupal-qa-tools --dev
```

4. (Optional) Copy the configuration files to your project root:

```bash
cp vendor/emhernapa/drupal-qa-tools/config/phpstan.neon .
cp vendor/emhernapa/drupal-qa-tools/config/phpmd.xml .
cp vendor/emhernapa/drupal-qa-tools/config/phpcs.xml .
```

---

## 🚀 Usage

- **PHPStan**:
  ```bash
  vendor/bin/phpstan analyse
  ```

- **PHPMD**:
  ```bash
  vendor/bin/phpmd web/modules/custom xml phpmd.xml
  ```

- **PHPCS**:
  ```bash
  vendor/bin/phpcs
  ```

---
