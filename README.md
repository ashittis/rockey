# 🔧 RocKey

RocKey is an AI-powered video keyframe processing tool that lets you:

- 🔍 Extract keyframes from videos (using scene detection)
- ✂️ Generate masks for objects using SAM (Segment Anything Model)
- 🧽 Remove objects via inpainting
- 🎨 Replace backgrounds using Stable Diffusion
- 🎞️ Composite keyframes into an AI-enhanced video
- 📺 Run all steps via CLI or a Streamlit UI

---

## 📦 Requirements

- Python 3.10 or 3.11
- A supported GPU (optional, but recommended for Stable Diffusion)
- Windows/macOS/Linux

Install dependencies:

```bash
pip install -r requirements.txt
````

---

## 🧠 Core Features

| Phase | Description                                     |
| ----- | ----------------------------------------------- |
| 1️⃣   | Keyframe Extraction using scene detection       |
| 2️⃣   | SAM-based Mask Generation for each keyframe     |
| 3️⃣   | Object Removal using OpenCV inpainting          |
| 4️⃣   | AI Background Generation using Stable Diffusion |
| 5️⃣   | Composite Subject + New Background              |
| 6️⃣   | Rebuild final video from edited frames          |

---

## 🖥️ CLI Usage

```bash
python main.py --video path/to/video.mp4 --generate-masks --remove-mask --genai-bg "cyberpunk city at night" --make-video
```

### 🔧 CLI Options

| Argument            | Description                                        |
| ------------------- | -------------------------------------------------- |
| `--video`           | Path to input video                                |
| `--out`             | Output folder for keyframes (default: `keyframes`) |
| `--threshold`       | Scene detection threshold (default: 30.0)          |
| `--generate-masks`  | Enable SAM-based mask generation                   |
| `--remove-mask`     | Inpaint masked regions from keyframes              |
| `--genai-bg PROMPT` | Generate AI background with prompt                 |
| `--make-video`      | Create final masked video                          |
| `--full-mask-video` | (Optional) Generate SAM masks for every frame      |

---

## 🌐 Streamlit App

To run the UI:

```bash
streamlit run app.py
```

### Features:

* Upload a video
* Adjust keyframe threshold
* One-click mask generation and object removal
* Enter a text prompt for background generation
* Preview AI-composited frames

---

## 📁 Project Structure

```
roki/
│
├── app.py                   ← Streamlit app entrypoint
├── main.py                  ← CLI entrypoint
├── rokey_pipeline.py        ← Core orchestration logic
├── requirements.txt
├── README.md
│
├── keyframes/               ← Extracted keyframes
├── masks/                   ← SAM-generated masks
├── removed/                 ← Inpainted keyframes
├── output/                  ← Composite output & AI backgrounds
├── video_input/             ← Uploaded videos
│
├── scripts/
│   ├── extract_keyframes.py
│   ├── generate_mask_sam.py
│   ├── remove_mask.py
│   ├── genai_background.py
│   ├── full_video_mask.py
│   └── make_video_from_masks.py
```
## 📸 Screenshots

![mask](https://github.com/ashittis/rockey/blob/main/Screenshot%202025-07-11%20181445.png)
![bgremove](https://github.com/ashittis/rockey/blob/main/Screenshot%202025-07-11%20182403.png)
![keyframe](https://github.com/ashittis/repot/blob/main/Screenshot%202025-07-11%20191820.png)
![genai](https://github.com/ashittis/repot/blob/main/Screenshot%202025-07-11%20192107.png)
![Indexing](https://github.com/ashittis/repot/blob/main/Screenshot%202025-07-11%20191820.png)
![Chat](https://github.com/ashittis/repot/blob/main/Screenshot%202025-07-11%20192107.png)

## 💾 Model Checkpoints

Make sure you place the following file in the root (or reference it):

* `sam_vit_b.pth` – Pretrained SAM model checkpoint

---

## ✨ Example Prompt Ideas

* `"futuristic laboratory interior"`
* `"lush jungle with ancient ruins"`
* `"empty desert road at sunset"`
* `"cyberpunk alleyway with neon lights"`

---

## 🛠️ Credits

* [Segment Anything (Meta)](https://github.com/facebookresearch/segment-anything)
* [Stable Diffusion (Stability AI)](https://github.com/CompVis/stable-diffusion)
* [SceneDetect](https://pyscenedetect.readthedocs.io)

---
