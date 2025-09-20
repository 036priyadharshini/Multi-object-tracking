
```markdown
# 🎯 Multi-Object Tracking Using BoostTrack++

A real-time multi-object tracking system designed to improve detection reliability and identity preservation in crowded or occluded environments. Built by integrating **YOLOX** with **BoostTrack++**, it enhances tracking accuracy through confidence boosting, adaptive thresholding, and tracklet similarity.

---

## 🚀 Features
- 🔎 **Soft Confidence Boosting** – recovers low-confidence but valid detections.
- 📉 **Tracklet Confidence Decay** – reduces identity switches during occlusion.
- 🔗 **Single-Stage Association** – efficient and scalable.
- 📊 **Benchmark Tested** – evaluated on MOT17 and MOT20.

---

## 🛠 Tech Stack
- **Languages:** Python  
- **Frameworks/Libraries:** PyTorch, OpenCV, Torchreid, YOLOX  
- **Other Tools:** YACS, ONNX Runtime, Loguru  


---

## ⚡ How It Works
1. **Detection:** YOLOX generates bounding boxes and initial confidences.  
2. **Similarity Check:** Soft Buffered IoU (SBIoU), Mahalanobis distance, and shape similarity used.  
3. **Confidence Boosting:** Low-confidence detections are re-evaluated and boosted.  
4. **Tracklet Decay:** Track confidence reduces when occluded/unmatched.  
5. **Association:** Single-stage association matches detections to tracklets.  

---

## 📊 Results
| Dataset | HOTA | MOTA | IDF1 | ID Switches |
|---------|------|------|------|-------------|
| MOT17   | 66.6 | 80.7 | 82.2 | 1062        |
| MOT20   | 66.4 | 77.7 | 82.0 | 762         |

✨ Achieved +9% HOTA, +8% MOTA, and +7% IDF1 over baseline BoostTrack, with ~20% fewer ID switches.

---

## ▶️ Getting Started
### 1. Clone the repo
```bash
git clone https://github.com/036priyadharshini/boosttrack-mot.git
cd boosttrack-mot
````

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run tracking

```bash
python src/tracking.py --video sample.mp4 --ckpt yolox_ckpt.pth
```
