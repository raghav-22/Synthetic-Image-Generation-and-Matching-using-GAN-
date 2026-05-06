🧠 Image Generation using GAN (TensorFlow)

This project implements a Generative Adversarial Network (GAN) using TensorFlow/Keras to generate synthetic images from a given dataset. The model learns the underlying distribution of input images and generates new realistic samples.

📌 Features
Custom GAN architecture (Generator + Discriminator)
Image preprocessing and dataset pipeline
Training with TensorFlow tf.data
Image generation and saving during training
Supports variable image resolutions
Loss tracking for Generator and Discriminator

🏗️ Project Structure
├── data/
│   ├── images/                # Training images
│   ├── output/                # Generated images
│   └── training_data.npy      # Preprocessed dataset (auto-generated)
│
├── notebook.ipynb             # Colab notebook (main code)
├── README.md
⚙️ Requirements

Install the required dependencies:

pip install tensorflow numpy pillow matplotlib tqdm

📂 Dataset
Place your training images inside:
/data/
Images will be:
Resized to required resolution
Normalized to range [-1, 1]

🧪 How It Works
1. Generator
Takes random noise vector (SEED_SIZE = 100)
Upsamples using Conv2D + BatchNorm
Outputs a synthetic image
2. Discriminator
CNN-based classifier
Distinguishes real vs fake images
3. Training Process
Generator tries to fool discriminator
Discriminator learns to detect fake images
Both networks improve together

🚀 Training
Update paths before running:

DATA_PATH = 'path_to_your_dataset'
Then run:
train(train_dataset, EPOCHS)
Default Parameters
Parameter	Value
Epochs	1000
Batch Size	32
Seed Size	100
Image Size	128x128 (configurable)

🖼️ Output
Generated images are saved in:
/data/output/
Example:
train-1.png
train-2.png
...

📊 Image Resolution Control
You can control output image size using:
GENERATE_RES = 4
GENERATE_RES	Image Size
1	32x32
2	64x64
3	96x96
4	128x128

🔍 Additional Experiment (Discriminator Testing)
The project also includes:
Testing discriminator on individual images
Comparing outputs between real and different images

💡 Notes
Training GANs is unstable — results may vary
More data improves quality
Tune hyperparameters for better performance

🤝 Contributing
Feel free to fork and improve the project!
