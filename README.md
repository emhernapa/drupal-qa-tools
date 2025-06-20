# Drupal QA Tools

Development tools for Drupal projects: PHPCS, PHPStan, PHPMD and Drupal coding standards ready to use.

## 🧠 Description

This repository provides a ready-to-use configuration of static analysis tools and coding standards for Drupal projects. It includes:

- **PHPCS** with Drupal coding standards  
- **PHPStan** for static code analysis  
- **PHPMD** for detecting problematic code  
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

2. (Optional) Add the following scripts to create the config files to your `composer.json`:

```json
"scripts": {
      "post-install-cmd": [
          "cp ./vendor/emhernapa/drupal-qa-tools/config/phpcs.xml phpcs.xml",
          "cp ./vendor/emhernapa/drupal-qa-tools/config/phpstan.neon phpstan.neon",
          "cp ./vendor/emhernapa/drupal-qa-tools/config/phpmd.xml phpmd.xml"
      ]
  }
```

3. Add the following scripts commangs to your `composer.json`:

```json
"scripts": {
      "test-phpcs": "./vendor/bin/phpcs",
      "test-phpstan": "./vendor/bin/phpstan analyse",
      "test-phpmd": "./vendor/bin/phpmd web/modules/custom xml phpmd.xml"
  }
```

4. Require it as a development dependency:

```bash
composer require emhernapa/drupal-qa-tools --dev
```

5. (Optional) Copy the configuration files to your project root:

```bash
cp ./vendor/emhernapa/drupal-qa-tools/config/phpcs.xml .
cp ./vendor/emhernapa/drupal-qa-tools/config/phpstan.neon .
cp ./vendor/emhernapa/drupal-qa-tools/config/phpmd.xml .
```

---

## 🚀 Usage

- **PHPCS**:
  ```bash
  ./vendor/bin/phpcs
  OR
  composer test-phpcs
  ```

- **PHPStan**:
  ```bash
  ./vendor/bin/phpstan analyse
  OR
  composer test-phpstan
  ```

- **PHPMD**:
  ```bash
  ./vendor/bin/phpmd web/modules/custom xml phpmd.xml
  OR
  composer test-phpmd
  ```

---
