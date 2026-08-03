

---
#  Soccer AI 🧠
## Demo
<p align="center">
  <img src="assets/outputs/1.png" alt="Image 1" width="400"/> 
  <img src="assets/outputs/2.png" alt="Image 2" width="400"/>
</p>
<p align="center">
  <img src="assets/outputs/3.png" alt="Image 3" width="400"/>
  <img src="assets/outputs/4.png" alt="Image 4" width="400"/>
</p>

Enlace a la [Demo](https://github.com/A7medM0sta/soccer/blob/main/data/2e57b9_0-radar.mp4)
## 📝 Descripción general
Investigación y desarrollo de modelos de IA para análisis y perspectivas de fútbol. Este proyecto tiene como objetivo proporcionar herramientas para detectar jugadores, porteros, árbitros y el balón en videos de fútbol. También incluye funciones para rastrear los movimientos de los jugadores, clasificarlos por equipos y visualizar las posiciones de los jugadores en el campo de fútbol.
### Entrenar detectores de balón
<p align="center">
  <div style="display: inline-block; margin: 10px;">
    <p><strong>Resultados de entrenamiento</strong></p>
    <img src="assets/img_1.png" alt="Train Results" width="400"/>
  </div>
  <div style="display: inline-block; margin: 10px;">
    <p><strong>Matriz de confusión</strong></p>
    <img src="assets/img.png" alt="Confusion Matrix" width="400"/>
  </div>
  <div style="display: inline-block; margin: 10px;">
    <p><strong>Resultado para validación</strong></p>
    <img src="assets/img_2.png" alt="Result for Validation" width="400"/>
  </div>
</p>

### Entrenar detectores de jugadores
<p align="center">
  <div style="display: inline-block; margin: 10px;">
    <p><strong>Resultados de entrenamiento</strong></p>
    <img src="assets/img_3.png" alt="Train Results" width="400"/>
  </div>
  <div style="display: inline-block; margin: 10px;">
    <p><strong>Matriz de confusión</strong></p>
    <img src="assets/img_5.png" alt="Confusion Matrix" width="400"/>
  </div>
  <div style="display: inline-block; margin: 10px;">
    <p><strong>Resultado para validación</strong></p>
    <img src="assets/img_4.png" alt="Result for Validation" width="400"/>
  </div>
</p>

### entrenar detectores de puntos clave del campo
<p align="center">
  <div style="display: inline-block; margin: 10px;">
    <p><strong>Resultados de entrenamiento</strong></p>
    <img src="assets/img_6.png" alt="Train Results" width="400"/>
  </div>
  <div style="display: inline-block; margin: 10px;">
    <p><strong>Resultado para validación</strong></p>
    <img src="assets/img_7.png" alt="Result for Validation" width="400"/>
  </div>
</p>

* Se desarrolló e integró Soccer AI utilizando YOLOv8, logrando más del 95% de precisión y un 85% de recuperación (recall) en la detección de jugadores, y un 99% de precisión y recuperación en la detección de puntos clave (keypoints) para el análisis de partidos de fútbol en tiempo real.
## 💻 Guía de instalación

Aún no disponemos de un paquete de Python, pero puedes instalarlo desde el código fuente en un entorno de [**Python>=3.8**](https://www.python.org/). Sigue los pasos a continuación:

```bash
pip install https://github.com/A7medM0sta/soccer.git
pip install -r requirements.txt
./setup.sh
```


## ⚙️ Modos

### 🏟️ Detección de campo
Detecta los límites y puntos clave del campo de fútbol en el video. Útil para identificar y visualizar la disposición del campo.

```bash
python main.py --source_video_path data/2e57b9_0.mp4 --target_video_path data/2e57b9_0-pitch-detection.mp4 --device mps --mode PITCH_DETECTION
```


### 🧑‍🤝‍🧑 Detección de jugadores
Detecta jugadores, porteros, árbitros y el balón en el video. Esencial para identificar y rastrear la presencia de jugadores y otras entidades en el campo.

```bash
python main.py --source_video_path data/2e57b9_0.mp4 --target_video_path data/2e57b9_0-player-detection.mp4 --device mps --mode PLAYER_DETECTION
```

### ⚽ Detección de balón
Detecta el balón en los fotogramas del video y rastrea su posición. Útil para seguir los movimientos del balón durante todo el partido.

```bash
python main.py --source_video_path data/2e57b9_0.mp4 --target_video_path data/2e57b9_0-ball-detection.mp4 --device mps --mode BALL_DETECTION
```

### 🏃‍♂️ Seguimiento de jugadores
Rastrea a los jugadores a lo largo de los fotogramas del video, manteniendo una identificación constante. Útil para seguir los movimientos y posiciones de los jugadores durante todo el partido.

```bash
python main.py --source_video_path data/2e57b9_0.mp4 --target_video_path data/2e57b9_0-player-tracking.mp4 --device mps --mode PLAYER_TRACKING
```


### 🏳️‍ Clasificación de equipos
Clasifica a los jugadores detectados en sus respectivos equipos basándose en sus características visuales. Ayuda a diferenciar a los jugadores de distintos equipos para análisis y visualización.

```bash
python main.py --source_video_path data/2e57b9_0.mp4 --target_video_path data/2e57b9_0-team-classification.mp4 --device mps --mode TEAM_CLASSIFICATION
```



### 🎯 Modo Radar
Combina la detección del campo, la detección de jugadores, el seguimiento y la clasificación de equipos para generar una visualización similar a un radar de las posiciones de los jugadores en el campo de fútbol. Proporciona una visión completa de los movimientos de los jugadores y las formaciones de los equipos.

```bash
python main.py --source_video_path data/2e57b9_0.mp4 --target_video_path data/2e57b9_0-radar.mp4 --device mps --mode RADAR
```



---



## Referencias
* http://roboflow.com
* https://github.com/roboflow/notebooks/blob/main/notebooks/train-yolov8-object-detection-on-custom-dataset.ipynb
* https://github.com/roboflow/notebooks
* https://blog.roboflow.com/camera-calibration-sports-computer-vision/* 
* https://blog.roboflow.com/tracking-ball-sports-computer-vision/
