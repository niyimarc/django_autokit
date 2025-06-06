# Django Autokit

**Django Autokit** is a CLI tool that automates the setup and maintenance of Django projects. It simplifies common tasks like environment variable setup, splitting settings into `base.py`, `dev.py`, and `prod.py`, generating `.env` files, and creating boilerplate apps — saving you time and effort when starting or scaling projects.

---

## ✨ Features

- 📁 Split `settings.py` into `base.py`, `dev.py`, and `prod.py`
- 🔐 Auto-generate a `.env` with `SETTINGS_PATH` and `ENV` variables
- 🧠 Automatically add new apps to `INSTALLED_APPS` (supports both flat and modular settings)
- 🔄 Compatible with Django 4.x and 5.x

---

## 📦 Installation

```bash
pip install django-autokit
```

---

## 🚀 Usage

Once installed, use the `djkit` CLI tool to run commands.

To see all available commands:

```bash
djkit --help
```

### 1️⃣ Initialize Autokit

In the root of your Django project, run:

```bash
djkit init-env
```

This will:

- Create a `.env` file if it doesn’t exist
- Set the `SETTINGS_PATH` (e.g., `yourproject.settings.base`)
- Add `ENV=dev` with a comment explaining how to switch to production
- Auto-detect and optionally split `settings.py` into modular settings

---

### 2️⃣ Split Settings Manually (Optional)

If not already split, you can do it manually with:

```bash
djkit split-settings
```

This will:

- Move your current `settings.py` into a `settings/` package
- Create `base.py`, `dev.py`, and `prod.py` for better configuration separation

---

### 3️⃣ Create a Django App

To generate a new app and automatically register it in `INSTALLED_APPS`:

```bash
djkit startapp blog
```

This will:

- Run `django-admin startapp blog`
- Automatically insert `'blog'` into your settings (flat or modular)

---

### 4️⃣ Gitignore Generator

To generate a Django-friendly `.gitignore` file:

```bash
djkit gitignore
```


## ⚙️ Environment Management

Your `.env` file will look like this:

```env
# Path to your Django settings file (use base.py for split settings)
SETTINGS_PATH=yourproject.settings.base

# Set ENV to 'prod' when deploying to production
ENV=dev
```

---

## 📁 Example Project Structure

```bash
yourproject/
├── manage.py
├── .env
├── yourproject/
│   ├── settings/
│   │   ├── base.py
│   │   ├── dev.py
│   │   └── prod.py
│   └── __init__.py
├── blog/
│   └── __init__.py
```

---

## ✅ Compatibility

- ✅ Django 4.x
- ✅ Django 5.x
- ✅ Python 3.7+

---

## 🛡 License

This project is licensed under the MIT License – see the [LICENSE](./LICENSE) file for details.

---

## 🤝 Contributing

Pull requests are welcome! If you find a bug or have a feature request, feel free to [open an issue](https://github.com/niyimarc/django_autokit/issues).

See full [Changelog](https://github.com/niyimarc/django_autokit/blob/master/CHANGELOG.md).

