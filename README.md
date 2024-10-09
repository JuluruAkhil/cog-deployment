# Image Classification with ResNet50

This project provides an image classification service using the ResNet50 model pre-trained on the ImageNet dataset. The service is implemented using [Cog](https://github.com/replicate/cog), which makes it efficient to run predictions in a consistent environment.

## Prerequisites

- Python 3.11
- Docker (for Cog)
- Git (for cloning the repository)

## Setup

1. **Clone the Repository:**

   ```bash
   git clone <repository-url>
   cd cog-test
   ```

2. **Install Cog:**

   First, ensure Docker is running on your machine. Then, install Cog following instructions from Cog's GitHub page.

3. **Download Model Weights:**

   The `cog.yaml` configuration file is set up to download model weights automatically during the build process. These weights are necessary for ResNet50 to run predictions.

## Usage

1. **Build the Prediction Environment:**

   Use Cog to build the environment needed to run predictions:

   ```bash
   cog build
   ```

2. **Run a Prediction:**

   Once built, you can run image predictions using:

   ```bash
   cog predict -i image=<path-to-image>
   ```

   Replace `<path-to-image>` with the path to your input image.

## Files

- `predict.py`: Contains the prediction logic using the ResNet50 model.
- `cog.yaml`: Configuration file for Cog specifying environment setup and model inference.
- `.gitignore`: Standard file to exclude certain files from version control.

## Notes

- Ensure your Docker service is running while using Cog, as it relies on Docker for containerization.
- The model weights and packages are specified in `cog.yaml` to keep setup consistent across different environments.

## License

This project is licensed under the MIT License. See the LICENSE file for more information.