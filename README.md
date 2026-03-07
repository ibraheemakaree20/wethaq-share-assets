# Wethaq Share Assets

This repository stores **image and video assets** used by the **Ayah sharing feature** in the Wethaq application.

The Flutter app fetches a single JSON file (`media.json`) that contains metadata and URLs for all media items.

This allows adding or removing media **without updating the mobile app**.

---

# Repository Structure

```
wethaq-share-assets/
│
├── data/
│   └── media.json
│
├── media/
│   ├── images/
│   │   ├── img_001.jpg
│   │   └── img_002.jpg
│   │
│   └── videos-data/
│       ├── videos/
│       │   ├── vid_001.mp4
│       │   └── vid_002.mp4
│       │
│       └── thumbnails/
│           ├── vid_001.jpg
│           └── vid_002.jpg
```

---

# media.json

`media.json` is the **index file** used by the mobile application.

The app downloads this file and uses it to display available images and videos.

Example:

```json
[
  {
    "id": "vid_001",
    "type": "video",
    "url": "media/videos-data/videos/vid_001.mp4",
    "thumbnailUrl": "media/videos-data/thumbnails/vid_001.jpg"
  },
  {
    "id": "vid_002",
    "type": "video",
    "url": "media/videos-data/videos/vid_002.mp4",
    "thumbnailUrl": "media/videos-data/thumbnails/vid_002.jpg"
  },
  {
    "id": "img_001",
    "type": "image",
    "url": "media/images/img_001.jpg"
  },
  {
    "id": "img_002",
    "type": "image",
    "url": "media/images/img_002.jpg"
  }
]
```

---

# Field Description

| Field        | Description                     |
| ------------ | ------------------------------- |
| id           | Unique identifier               |
| type         | `image` or `video`              |
| url          | Path to media file              |
| thumbnailUrl | Preview image (only for videos) |

---

# How the Mobile App Uses This

### 1. Fetch media list

The Flutter app downloads:

```
data/media.json
```

### 2. Build UI

The app displays:

* images directly
* video thumbnails for videos

### 3. Load media

When the user selects an item:

* Images load directly.
* Videos load using the video URL.

---

# Adding New Media

### Adding an Image

1. Upload the image to:

```
media/images/
```

Example:

```
media/images/img_003.jpg
```

2. Add an entry in `media.json`:

```json
{
  "id": "img_003",
  "type": "image",
  "url": "media/images/img_003.jpg"
}
```

---

### Adding a Video

1. Upload the video to:

```
media/videos-data/videos/
```

Example:

```
media/videos-data/videos/vid_003.mp4
```

2. Create a thumbnail image.

Upload to:

```
media/videos-data/thumbnails/
```

Example:

```
media/videos-data/thumbnails/vid_003.jpg
```

3. Add entry in `media.json`:

```json
{
  "id": "vid_003",
  "type": "video",
  "url": "media/videos-data/videos/vid_003.mp4",
  "thumbnailUrl": "media/videos-data/thumbnails/vid_003.jpg"
}
```

---

# File Naming Rules

Use the following format:

```
img_001.jpg
img_002.jpg

vid_001.mp4
vid_002.mp4
```

Rules:

* lowercase letters only
* use `_` instead of spaces
* keep numbering sequential

