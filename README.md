# DDIM Inversion and Latent Interpolation

This repository implements the Denoising Diffusion Implicit Models (DDIM) inversion method to invert real images into latent representations. It also generates new images via linear interpolation of the inverted latents.

## Features

1. **DDIM Inversion**: Get latent representations of real images.
2. **Latent Interpolation**: Perform linear interpolation on the latents to generate new images.
3. **Image Generation**: Sample images from a pre-trained DDIM model.
4. **Visualization**: Visualize interpolated images in a grid layout.

---

## Installation

### Prerequisites

Ensure you have the following installed:
- Python 3.8+
- PyTorch 1.12+
- CUDA-enabled GPU (recommended)

### Steps

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/DDIM-Inversion.git
    cd DDIM-Inversion
    ```
2. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Download datasets and place them in the `data` directory:
    - Butterfly Dataset: `data/butterfly_data/`
    - Animal Dataset: `data/Animals_data/animals/`

---

## Usage

### Training DDIM

Train the DDIM model with the following command:
```bash
python train_ddim.py
```

### DDIM Inversion

Invert real images to their latent representations:
```bash
python invert_images.py --input_dir "path/to/real/images" --output_dir "path/to/save/latents"
```

### Latent Interpolation

Generate new images by interpolating between the latents of two images:
```bash
python latent_interpolation.py --latents_dir "path/to/latents" --output_dir "path/to/save/interpolations"
```

### Visualization

Plot generated images or interpolation results:
```bash
python visualize_results.py --images_dir "path/to/images" --output_file "output_plot.png"
```

---

## Repository Structure

```plaintext
.
├── data/                    # Datasets
├── DDIM/                    # Model checkpoints and logs
├── scripts/                 # Utility scripts
│   ├── train_ddim.py        # Training script for DDIM
│   ├── invert_images.py     # Image inversion script
│   ├── latent_interpolation.py # Latent interpolation script
│   └── visualize_results.py # Visualization script
├── models/                  # Model definitions (e.g., UNet)
├── requirements.txt         # Python dependencies
├── README.md                # Project README
└── examples/                # Example generated images
```

---

## Example Results

### Inverted Images
Visualize how real images are reconstructed using DDIM.

### Interpolated Images
Generated images obtained by linearly interpolating between latent representations.

---

## Configuration

All hyperparameters are defined at the top of the respective scripts. Key parameters include:
- `IMG_SIZE`: Size of images (default: 128x128).
- `BATCH_SIZE`: Training batch size (default: 128).
- `NUM_EPOCHS`: Number of training epochs (default: 600).
- `NOISE_STEPS`: Steps for noise addition during diffusion.
- `SAMPLING_STEPS`: Steps for image generation during sampling.

---

## Contributions

Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch for your feature/bug fix.
3. Submit a pull request.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

This implementation references the original [DDIM paper](https://arxiv.org/abs/2010.02502). Special thanks to the PyTorch and TensorFlow communities for their support.
