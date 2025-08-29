## Project Description

**ShoeGAN** is a deep learning project that demonstrates edge-to-photo image translation using a conditional Generative Adversarial Network (GAN) based on the Pix2Pix architecture. The model is trained to generate realistic shoe images from edge maps, enabling applications such as sketch-based shoe design, data augmentation, and creative AI art.  
The project leverages PyTorch and the `torch_snippets` utility library for streamlined data handling and visualization.  
**Achievements:**  
- Successfully trained a GAN to convert edge-detected shoe images into realistic colored shoe photos.
- Implemented a custom dataset loader with color-point augmentation for improved learning.
- Provided a reproducible notebook with all code, training, and visualization steps.

---

## How to Run This Project

### 1. Clone or Download the Repository

```sh
git clone https://github.com/yourusername/ShoeGAN.git
cd ShoeGAN
```
Or download the notebook file (shoegan.ipynb) and place it in your working directory.

### 2. Install Required Dependencies

You can install the required Python packages using pip.  
**Recommended:** Use a virtual environment.

```sh
pip install torch torchvision torch_snippets torchsummary scikit-learn opencv-python
```

If running in a Jupyter environment, you can install missing packages directly in a cell:

```python
!pip install -U torch_snippets torchsummary scikit-learn opencv-python
```

### 3. Download the Dataset

The notebook automatically downloads and unzips the [ShoeV2_photo.zip](https://www.dropbox.com/s/g6b6gtvmdu0h77x/ShoeV2_photo.zip) dataset if not present:

```python
import os
if not os.path.exists('ShoeV2_photo'):
    !wget https://www.dropbox.com/s/g6b6gtvmdu0h77x/ShoeV2_photo.zip
    !unzip -q ShoeV2_photo.zip
```

### 4. Run the Notebook

Open shoegan.ipynb in Jupyter Notebook, JupyterLab, or VS Code and run all cells sequentially.  
The notebook will:
- Prepare the dataset and perform edge detection.
- Define the custom `ShoesData` dataset class.
- Build and initialize the Pix2Pix (U-Net Generator and PatchGAN Discriminator) models.
- Train the GAN and visualize results after each epoch.

### 5. Training and Results

- Training progress and sample outputs are displayed inline in the notebook.
- The model is trained for 100 epochs by default; you can adjust this as needed.
- After training, you can generate new shoe images from edge maps using the trained generator.

---

## Project Structure

- shoegan.ipynb — Main Jupyter notebook with all code, training, and visualization.
- `ShoeV2_photo/` — Folder containing the shoe images (downloaded automatically).
- No additional scripts or modules are required.

---

## Notes

- This project is intended for educational and research purposes.
- For best results, run on a machine with a CUDA-compatible GPU.
- You can experiment with your own edge images or modify the dataset for other objects.

---

## Credits

- Dataset: [ShoeV2_photo](https://www.dropbox.com/s/g6b6gtvmdu0h77x/ShoeV2_photo.zip)
- Pix2Pix architecture: [Isola et al., 2017](https://arxiv.org/abs/1611.07004)
- Utility functions: [`torch_snippets`](https://github.com/bhansaliakhil/torch_snippets)

---

## License

This project is released under the MIT License.  
Feel free to fork, modify, and use for your own research or creative projects!
