# Hand Gesture Recognition Project

## Step-by-Step Guide to Run the Project

### Step 1: Setup Environment

1. Create a new virtual environment (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

2. Install required packages:
   ```bash
   pip install opencv-python mediapipe numpy scikit-learn matplotlib
   ```

### Step 2: Data Collection

1. Run the collection script:
   ```bash
   python collection.py
   ```

2. For each number/gesture (0-9):
   - The webcam window will open
   - Press 'Q' when ready to start capturing
   - Hold your hand gesture steady
   - The script will automatically capture 100 images
   - Repeat for all numbers/gestures

### Step 3: Create Dataset

1. Run the dataset creation script:
   ```bash
   python datasetcreation.py
   ```

2. This will:
   - Process all your captured images
   - Create a data.pickle2 file containing the processed data

### Step 4: Run Recognition System

Choose one of the following based on what you want to recognize:

1. For Number Recognition (0-9):
   ```bash
   python classifier_for_num.py
   ```

2. For Alphabet Recognition (A-Z):
   ```bash
   python alphabet.py
   ```

### Expected Output

- A webcam window will open
- Hold your hand in front of the camera
- A bounding box will appear around your hand
- The predicted gesture/number will be displayed above the box

### Important Notes

1. **Directory Structure**
   Make sure you have:
   ```
   project/
   ├── data2/              # Created during data collection
   ├── model.p             # Created after training
   ├── collection.py
   ├── datasetcreation.py
   ├── classifier_for_num.py
   └── alphabet.py
   ```

2. **Webcam Access**
   - Ensure your webcam is connected and working
   - Grant necessary permissions when prompted

3. **Lighting and Position**
   - Use good lighting
   - Keep your hand within frame
   - Maintain a steady position
   - Use a clean background

4. **Exit Programs**
   - Press 'Q' to exit from the webcam windows
   - Or use Ctrl+C in the terminal

### Troubleshooting

If you encounter issues:

1. **No Webcam Found**
   ```python
   # Try changing in the relevant .py file:
   cap = cv2.VideoCapture(1)  # Instead of VideoCapture(0)
   ```

2. **Model Not Found Error**
   - Ensure model.p is in the same directory
   - Run data collection and creation steps first

3. **Poor Recognition**
   - Try recollecting data with better lighting
   - Ensure hand gestures are clear and consistent
   - Keep hand within the camera frame

### For Best Results

1. During Data Collection:
   - Vary hand position slightly
   - Maintain consistent lighting
   - Use different angles
   - Keep background clean

2. During Recognition:
   - Hold gestures steady
   - Ensure good lighting
   - Keep hand within frame
   - Maintain appropriate distance from camera

## Troubleshooting

Common Issues and Solutions:

1. **Webcam Not Detected**
   - Check webcam connections
   - Verify webcam permissions
   - Try changing `cv2.VideoCapture(0)` to `cv2.VideoCapture(1)`

2. **Poor Recognition**
   - Improve lighting conditions
   - Retrain model with more diverse data
   - Keep hand within frame bounds
   - Maintain consistent distance

3. **Model Loading Error**
   - Verify model.p exists in correct directory
   - Check Python version compatibility
   - Reinstall required packages

## Best Practices

1. **Data Collection**
   - Collect data in various lighting conditions
   - Include slight variations in hand positions
   - Use clean, contrasting background
   - Maintain consistent hand orientation

2. **During Recognition**
   - Keep hand steady
   - Ensure good lighting
   - Position hand within frame
   - Maintain appropriate distance from camera

3. **System Optimization**
   - Close other camera applications
   - Run on dedicated GPU if available
   - Regular model retraining
   - Keep software updated

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- MediaPipe team for hand detection framework
- OpenCV community for computer vision tools
- Contributors and testers
