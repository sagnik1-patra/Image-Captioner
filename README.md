An advanced Image Caption Generator using:

 CNN+LSTM (TensorFlow/Keras) – your custom trained model

 BLIP-2 (HuggingFace Transformers) – to refine captions for richer, human-like results

This system takes any image and generates a descriptive caption.

 Features
 Trains a CNN+LSTM caption generator using Flickr8k captions
 Saves model in modern .keras format (Keras 3.x compatible)
 Inference script supports:

Local .keras model for base captions

BLIP-2 API for enhanced captions
 Works on any new image

 Project Structure
nginx
Copy
Edit
Image Captioner/
├── archive (1)/
│   ├── captions.txt        # Flickr8k captions file
│   └── Images/             # Flickr8k images folder
├── image_caption_model.keras # Trained Keras model
├── tokenizer.pkl           # Saved tokenizer
├── generate_caption.py     # Inference script
├── hybrid_caption.py       # Your model + BLIP-2 hybrid script
├── train_caption_model.py  # Training script
├── README.md               # This file
 Requirements
Install dependencies:

bash
Copy
Edit
pip install tensorflow==2.14.0 transformers pillow torch tqdm
🏃‍♂️ Training
Train your CNN+LSTM caption generator:

bash
Copy
Edit
python train_caption_model.py
This will:

Extract InceptionV3 features

Train model on Flickr8k

Save:

image_caption_model.keras

tokenizer.pkl

 Generate Captions (Local Model)
To generate captions using your trained model:

bash
Copy
Edit
python generate_caption.py --image "path/to/your/image.jpg"
Example:

bash
Copy
Edit
python generate_caption.py --image "C:\Users\sagni\Downloads\Image Captioner\WhatsApp Image 2025-07-21 at 14.39.35_c9b4dbd3.jpg"
Output:

less
Copy
Edit
 Generated Caption: a man in a blue shirt sitting on a bench with a bottle
