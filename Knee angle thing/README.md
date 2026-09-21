# Knee ROM Tracker

An entirely private, web-based tool for tracking knee extension and flexion using AI Pose Estimation. 

## Features
* **100% Private**: Runs entirely in your local browser using JavaScript. No video is uploaded to the internet.
* **Camera Overlay Mode (`index.html`)**: Shows your camera feed, drawing lines over your leg and calculating the true 3D angle. Tracks your maximum extension and flexion during a session.
* **3D Spatial Model Mode (`3d_model_tracker.html`)**: Extracts the 3D data points of your hip, knee, and ankle, and drops them into an interactive 3D space. You can drag and rotate the screen to view the actual 3D model the AI is generating of your leg in real time.

## Setup via GitHub Desktop & GitHub Pages
Since this is a Progressive Web App, you can host it for free on GitHub Pages to access it on your phone:

1. Open **GitHub Desktop** and add this `Knee angle thing` folder as a local repository.
2. Publish the repository to your GitHub account.
3. Go to github.com, open the repository settings.
4. Navigate to **Pages** (on the left sidebar).
5. Under "Build and deployment", set the Source to **Deploy from a branch**, and choose your `main` or `master` branch.
6. Save. In a minute or two, GitHub will give you a live URL.
7. Open that URL on your phone's browser (Safari/Chrome).

**Note**: When you open it on your phone, you must grant Camera permissions for the AI to track your motion.

## Technical Details
This application uses Google's `MediaPipe Pose` AI model. It utilizes `poseWorldLandmarks` to extract true 3D coordinates (X, Y, Z in meters) rather than just flat pixel coordinates. This allows the trigonometry math to accurately calculate the angle of the knee regardless of oblique camera perspectives.
