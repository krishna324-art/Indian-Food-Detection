---
title: Indian-food Calorie-count
emoji: 🦀
colorFrom: indigo
colorTo: gray
sdk: gradio
sdk_version: 5.44.1
app_file: app.py
pinned: false
license: apache-2.0
---

Check out the :https://huggingface.co/spaces/kinsu2/indian-food_calorie-count
🍛 Indian Food Detection & Calorie Estimator

This project uses a YOLOv8 object detection model to detect Indian dishes from images.
The primary task is object detection (identifying which dish is present and where).
On top of detection, we estimate calories using bounding box area scaling.

✨ Features
Detects multiple Indian dishes in one image.

Estimates calories using bounding box scaling logic.

Interactive Gradio web app for easy use.

Built with ultralytics, opencv-python, torch, and gradio.

📂 Detected Dishes (Classes)
The model has been trained to detect the following dishes:

🥔🥦 Aloo Gobi
🥔🍛 Aloo Masala
🍞 Bhatura
🌿🍲 Bhindi Masala
🍗🍚 Biryani
🍵 Chai
🥘 Chole
🥥🥣 Coconut Chutney
🥣 Dal
🥞 Dosa
🥔 Dum Aloo
🐟🍛 Fish Curry
🍮 Ghevar
🌿 Green Chutney
🍯 Gulab Jamun
🥞 Idli
🍯 Jalebi
🍢 Kebab
🍚 Kheer
🍦 Kulfi
🥤 Lassi
🍖 Mutton Curry
🧅 Onion Pakoda
🌿🧀 Palak Paneer
🍋 Poha
🫘 Rajma Curry
🍮 Ras Malai
🥟 Samosa
🧀🍛 Shahi Paneer
🍚 White Rice
🧮 Calorie Count Logic
Each dish has a base calorie value (e.g., 1 slice of pizza = 285 kcal).

When the model detects a dish, it also gives a bounding box around it.

We compute the detected area = (x2 - x1) × (y2 - y1).

We compare it with the average reference area of that dish from the training set.

Calories are scaled by the ratio:

[ \text{Calories} = \text{BaseCalories} \times \frac{\text{DetectedArea}}{\text{ReferenceAvgArea}} ]

If multiple dishes are detected, their calories are added together to get the total calories.
