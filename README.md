# Kanad - IoT-Enabled Precision Agriculture System

**Kanad** is an Internet of Things (IoT)-enabled irrigation system that leverages deep learning technologies to optimize water usage, improve crop health, and suggest fertilizer use based on real-time data. Kanad integrates multiple sensors, machine learning, and a user-friendly interface to help farmers make data-driven decisions regarding irrigation, crop growth, and disease prediction.

## Key Features

- **Smart Irrigation**: Uses IoT sensors to collect real-time soil moisture and atmospheric conditions. The data is processed using an LSTM neural network to predict future moisture levels and suggest optimal irrigation times.
  
- **Crop Suggestion**: NPK sensors measure soil nutrient levels, and using a deep learning model, Kanad suggests the most suitable crops for the given soil conditions.

- **Fertilizer Suggestion**: Based on NPK levels detected, the system provides recommendations for fertilizers to help maintain soil health.

- **Crop Disease Prediction**: Farmers upload images of their crops, which are analyzed by a CNN-based model to detect crop diseases with over 95% accuracy.

## Technology Stack

- **IoT**: Sensors for real-time data collection (soil moisture, NPK levels).
- **Machine Learning**:
  - **LSTM Neural Networks** for irrigation prediction.
  - **CNN (ResNet50)** for crop disease detection.
- **Python**: Used for machine learning models.
- **Flask**: Backend API for communication.
- **Heroku**: Cloud deployment for web and backend servers.
- **Raspberry Pi**: Manages real-time data from sensors and controls irrigation.

## Mathematical Explanation of Model Preprocessing

### Smart Irrigation

Kanad collects data from IoT sensors in the farm field, including soil moisture, and environmental data. The LSTM neural network processes this data and predicts future moisture levels, optimizing irrigation schedules.

**Equation for LSTM-based prediction**:

<img src="https://latex.codecogs.com/png.latex?%5Chat%7By%7D(t%2B1)%20%3D%20%5Csigma(W_%7By%7D%20h_t%20%2B%20b_y)" alt="LSTM Equation">

Where:
- <img src="https://latex.codecogs.com/png.latex?%5Chat%7By%7D(t%2B1)" alt="y_hat"> is the predicted soil moisture level at time <img src="https://latex.codecogs.com/png.latex?t%2B1">.
- <img src="https://latex.codecogs.com/png.latex?h_t"> is the hidden state at time \( t \).
- \( W_{y} \) and \( b_y \) are the weights and biases of the LSTM output layer.
- \( \sigma \) is the activation function.

#### Image: Smart Irrigation Workflow

![Smart Irrigation Workflow](https://imgur.com/yk4vpv9.png)

### Crop Suggestion Module

The system suggests crops based on NPK levels detected by sensors. This module uses soil nutrient data, location, and a deep learning model to recommend the best crops.

**Crop Suggestion Workflow**:
1. Farmer inputs NPK values.
2. The model provides crop recommendations based on soil data and location.

#### Image: User Fills NPK Levels

![NPK Levels Input](https://imgur.com/Lm86yyx.png)

#### Image: Crop Suggestion Results

![Crop Suggestion Results](https://imgur.com/5LashLI.png)

### Fertilizer Suggestion

Using NPK sensor data, Kanad provides recommendations for fertilizers to help maintain soil health. It prevents overuse of fertilizers and encourages sustainable farming practices.

#### Image: Fertilizer Suggestion Results

![Fertilizer Suggestion Results](https://imgur.com/y0BAV8w.png)

### Crop Disease Prediction

Farmers can upload crop images to detect diseases using the CNN model (ResNet50). The model analyzes crop images with an accuracy rate of 95.25%.

**CNN Equation for disease detection** (Cross-Entropy Loss Function):

<img src="https://latex.codecogs.com/png.latex?L(y,%20%5Chat%7By%7D)%20%3D%20-%5Csum_%7Bi%7D%20y_i%20%5Clog(%5Chat%7By%7D_i)" alt="Cross-Entropy Equation">

Where:
- \( L \) is the loss function.
- \( y_i \) is the true label of the crop disease.
- \( \hat{y}_i \) is the predicted probability.

#### Image: Uploading Crop Image

![Crop Disease Image Upload](https://imgur.com/KHW2mMZ.png)

#### Image: Crop Disease Results

![Crop Disease Results](https://imgur.com/Me3aRpM.png)

## Installation

### Prerequisites

- **Raspberry Pi**: Set up to manage sensors and control irrigation.
- **IoT Sensors**: Soil moisture, NPK, and atmospheric sensors.
- **Heroku Account**: Cloud deployment for the model.
- **Python 3.x**: Required for running the machine learning models.
- **Flask**: Backend API framework.

### Steps

1. Clone the repository:
    ```bash
    git clone https://github.com/kanad-project/kanad.git
    cd kanad
    ```

2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Set up IoT sensors with Raspberry Pi for real-time data collection.

4. Deploy the web app and backend to Heroku:
    ```bash
    heroku create
    git push heroku main
    ```

5. Open the web app and start using Kanad to manage irrigation, crop prediction, and disease detection.

### Usage

1. **Smart Irrigation**:
   - View real-time soil data on the dashboard.
   - The system automatically schedules irrigation based on moisture predictions.

#### Image: Smart Irrigation Dashboard

![Smart Irrigation Dashboard](https://imgur.com/EBFP2Wf.png)

2. **Crop and Fertilizer Suggestions**:
   - Input soil NPK values through the app.
   - Get suggestions for crops and fertilizers based on real-time data.

#### Image: Crop and Fertilizer Input

![Crop Fertilizer Input](https://imgur.com/HyDEkV2.png)

3. **Disease Detection**:
   - Upload crop images to the web app.
   - Get disease detection results and treatment suggestions.

#### Image: Disease Detection Results

![Disease Detection Results](https://imgur.com/lft6PIT.png)

## Future Improvements

- **Rainfall Prediction Module**: Incorporate weather data for rainfall prediction to prevent over-irrigation.
- **User Feedback Integration**: Gather feedback from farmers and stakeholders to enhance system features.
- **Collaboration with Local Authorities**: Expand testing and usage with local farming administrations.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Paper and Research

For detailed insights into the development of **Kanad**, please refer to the paper:

[Integration of IoT in Irrigation: Kanad](./Executive_Summary.pdf)

## Contact

For any questions or issues, please contact:

- **Ansh Tiwari** (anshtiwari9899@gmail.com)
