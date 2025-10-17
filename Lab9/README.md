# Lab9 — GAN and CGAN MNIST Experiments

This folder contains two Jupyter notebooks for the lab: `GAN_MNIST_Dataset.ipynb` and `CGAN_MNIST_DataSet.ipynb`.

What I changed/added:
- Added configurable `LATENT_DIM` and `OUT_DIR` for saving outputs.
- Added utilities to save generated images and create GIFs showing progression.
- Made generator/discriminator/gan builders accept configurable latent dims and optimizers.
- Implemented label smoothing option in the CGAN training function.
- Added interpolation helper to create morphing sequences between two digit conditions.
- Added markdown guidance cells describing how to run the experiments and what to observe.

How to run in Google Colab:
1. Upload this folder to your Google Drive or open the notebook directly in Colab (File -> Upload notebook).
2. Install requirements if needed (Colab already has TensorFlow). To be safe, run:

```powershell
!pip install --upgrade tensorflow imageio
```

3. In `GAN_MNIST_Dataset.ipynb` or `CGAN_MNIST_DataSet.ipynb`:
   - Set `LATENT_DIM` to 50 / 100 / 200 as required.
   - (Re)build models: `generator = build_generator(LATENT_DIM)` and `discriminator = build_discriminator()`.
   - Build GAN with chosen optimizers: `gan = build_gan(generator, discriminator, gen_optimizer=..., disc_optimizer=..., latent_dim=LATENT_DIM)` for GAN notebook.
   - Run training. For the full experiment set `epochs=10000` and `save_interval=1000`. Note: full training can take many hours on Colab; use GPU runtime.

4. Download GIFs from `gan_outputs` or `cgan_outputs` after training for inclusion in your report.

Notes and tips:
- For quick verification, run epochs=1 and save_interval=1 to make sure code runs in your environment.
- If you run into memory issues, reduce `batch_size`.


