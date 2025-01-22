# AI-Web-App-to-recognize-vehicle-types and brands
Web app to detect the car types and brands using object detection and custom labels


# Car Detection App

## Overview
The Car Detection App is designed to detect car types and its brands using machine learning models.

## Features
- Detect cars in images
- Display detection results with bounding boxes
- User-friendly interface

## Installation
1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/car-detection-app.git
    ```
2. Navigate to the project directory:
    ```bash
    cd car-detection-app
    ```
3. Install the dependencies:
    ```bash
    npm install
    ```

## Usage
1. Start the application:
    ```bash
    npm run dev
    ```
2. Open your browser and navigate to `http://localhost:5173`.

# Car Detection Server (Azure)

## Overview

The Car Detection Server is an Azure-based backend service for the Car Detection App. It handles image processing and car detection using machine learning models.

## Features

- Process images for car detection
- Serve detection results to the frontend app
- Scalable and reliable Azure infrastructure

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/hamzagodme/car-detection-server-azure.git
   ```
2. Navigate to the project directory:
   ```bash
   cd car-detection-server-azure
   ```
3. Install the dependencies:

   ```bash
   npm install express cors dotenv

   ```

3. Create a `.env` file in the root directory and add the following environment variables:
    ```
    CUSTOM_VISION_ENDPOINT=<your-custom-vision-endpoint>
    TYPE_PROJECT_ID=<your-type-project-id>
    BRAND_PROJECT_ID=<your-brand-project-id>RV
    PREDICTION_KEY=<your-prediction-key>
    ```

## Training the Azure Custom Vision Model

1. Go to the [Azure Custom Vision](https://www.customvision.ai/) portal and sign in with your Azure account.

2. Create a new project for detecting car types:
    - Click on "New Project".
    - Enter a name and description.
    - Select "Classification" for the project type.
    - Choose "Multiclass (Single tag per image)".
    - Select a domain that fits your needs (e.g., General).

3. Upload and tag images for different car types. Train the model and publish the iteration. Note the `Project ID` and `Iteration Name`.

4. Repeat the above steps to create another project for detecting car brands:
    - This time, select "Object Detection" for the project type.

5. After training and publishing both models, go to the "Prediction URL" tab and note the `Endpoint` and `Prediction-Key`.

## Running the Server

1. Start the server:
    ```sh
    npm start
    ```

2. The server will be running on `http://localhost:5000`.

## API Endpoint

- `POST /analyze-car`
    - Content-Type: `image/*`
    - Body: Raw image data
    - Response: JSON object containing the detected car type and brand.

    Example:
    ```sh
    curl -X POST http://localhost:5000/analyze-car -H "Content-Type: image/jpeg" --data-binary "@path/to/car/image.jpg"
    ```

    Response:
    ```json
    {
      "type": "Sedan",
      "brand": "Toyota"
    }
    ```
## Usage

1. Start the server locally:
   ```bash
   npm start
   ```
2. The server will be running at `http://localhost:5000`.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes.

## License

This project is licensed under the MIT License.


