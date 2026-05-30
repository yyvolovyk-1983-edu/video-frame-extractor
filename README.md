<div align="center">

# video-frame-extractor

**Збереження кадрів з відеофайлу за допомогою Python та OpenCV**

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://github.com/yyvolovyk-1983-edu/video-frame-extractor)
[![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)](https://github.com/yyvolovyk-1983-edu/video-frame-extractor)

</div>

---

## Що робить

Витягує окремі кадри з відеофайлу та зберігає їх як зображення JPEG.

```
відеофайл → OpenCV читає кадри → зберігає frame_0001.jpg, frame_0002.jpg ...
```

---

## Встановлення

```bash
git clone https://github.com/yyvolovyk-1983-edu/video-frame-extractor
cd video-frame-extractor
pip install opencv-python
```

---

## Використання

```python
import cv2, os

def extract_frames(video_path, output_dir="frames", step=1):
    os.makedirs(output_dir, exist_ok=True)
    cap = cv2.VideoCapture(video_path)
    frame_idx = 0

    while cap.isOpened():
        ret, frame = cap.read()
        if not ret:
            break
        if frame_idx % step == 0:
            cv2.imwrite(f"{output_dir}/frame_{frame_idx:04d}.jpg", frame)
        frame_idx += 1

    cap.release()
    print(f"Збережено кадрів: {frame_idx // step}")

extract_frames("video.mp4", step=30)  # кожен 30-й кадр
```

---

## Параметри

| Параметр | Опис | За замовчуванням |
|---|---|---|
| `video_path` | Шлях до відеофайлу | — |
| `output_dir` | Папка для збереження кадрів | `frames/` |
| `step` | Кожен N-й кадр зберігати | `1` (всі) |

---

## Залежності

```
opencv-python
```

---

## Пов'язаний проект

Хочете з кадрів зробити GIF?
→ [video-to-gif](https://github.com/yyvolovyk-1983-edu/video-to-gif)

---

<div align="center">

**Автор:** [Євген Воловик](https://github.com/yyvolovyk-1983-edu) · Харків, Україна
📧 y.y.volovyk@student.khai.edu · [LinkedIn](https://www.linkedin.com/in/yevhen-volovyk/)

</div>