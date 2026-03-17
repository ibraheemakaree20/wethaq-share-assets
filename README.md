# Wethaq Share Assets

This repository contains media assets used in the **Wethaq App** for generating and sharing Quran Ayah content (images & videos).

---

## 📁 Structure

```
assets/
  images/            # Local images
  videos/            # Local videos

data/
  media.json         # Media configuration file

README.md
```

---

## 📦 media.json Format

All media is defined inside `data/media.json`.

### Example:

```json
[
  {
    "id": "vid_001",
    "type": "video",
    "source": "local",
    "url": "..."
  },
  {
    "id": "vid_006",
    "type": "video",
    "source": "external",
    "url": "..."
  },
  {
    "id": "img_001",
    "type": "image",
    "source": "local",
    "url": "..."
  }
]
```

---

## 🧩 Fields Explanation

| Field    | Description                                   |
| -------- | --------------------------------------------- |
| `id`     | Unique identifier (e.g. `vid_001`, `img_001`) |
| `type`   | `"video"` or `"image"`                        |
| `source` | `"local"` or `"external"`                     |
| `url`    | File path (local) or direct URL (external)    |

---

## 🌐 Media Sources

### Local Media

Stored inside the repository:

```
assets/videos/
assets/images/
```

Used for:

* fast loading
* offline usage

---

### External Media

External media (e.g. from Pixabay) is referenced via direct URLs:



---

## ⚡ Usage in App

The app:

1. Fetches `media.json`
2. Displays available images/videos
3. Allows user to select media
4. Generates Ayah content:

   * overlays Quran text
   * adds recitation audio
   * applies branding (Wethaq logo)

---

## ⚖️ Licensing

Some media assets are sourced from external platforms such as Pixabay.

* Used under the Pixabay License
* Media is incorporated into a larger work (Wethaq app)
* Final generated content includes:

  * Quran Ayah
  * Audio recitation

---

## 🚀 Notes

* This repository is used as a **media backend** for the app
* Media may be updated or replaced without changing app code
* Supports both local and external sources



---
