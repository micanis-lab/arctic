# ARCTIC dataset downloader

This fork retains only the code and documentation needed to download, verify,
and unpack the ARCTIC dataset for Akagi experiments. Training, evaluation,
rendering, visualization, and baseline-model code have been removed.

The original project is
[`zc-alexfan/arctic`](https://github.com/zc-alexfan/arctic). See `LICENSE` and
cite the original ARCTIC paper when using the data.

## Requirements

Register accounts for:

- [ARCTIC](https://arctic.is.tue.mpg.de/register.php)
- [SMPL-X](https://smpl-x.is.tue.mpg.de/)
- [MANO](https://mano.is.tue.mpg.de/)

Create an isolated Python environment and install the downloader dependencies:

```bash
python3.10 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Export credentials without committing them:

```bash
export ARCTIC_USERNAME="..."
export ARCTIC_PASSWORD="..."
export SMPLX_USERNAME="..."
export SMPLX_PASSWORD="..."
export MANO_USERNAME="..."
export MANO_PASSWORD="..."
```

## Smoke download

Run all commands from this directory:

```bash
bash/download_dry_run.sh
python scripts_data/checksum.py
python scripts_data/unzip_download.py
```

## Data required by Akagi exp003

Download full-resolution images, metadata, official splits, and body models:

```bash
bash/download_images.sh
bash/download_misc.sh
bash/download_splits.sh
bash/download_body_models.sh
python scripts_data/checksum.py
python scripts_data/unzip_download.py
```

The scripts write archives to `downloads/` and extracted data to `unpack/`.
Move the extracted result to the Akagi root data directory after verification.
Both directories are local artifacts and must not be committed.

See:

- `docs/data/README.md` for the official download description.
- `docs/data/data_doc.md` for the downloaded data schema.

## Citation

```bibtex
@inproceedings{fan2023arctic,
  title = {{ARCTIC}: A Dataset for Dexterous Bimanual Hand-Object Manipulation},
  author = {Fan, Zicong and Taheri, Omid and Tzionas, Dimitrios and Kocabas,
            Muhammed and Kaufmann, Manuel and Black, Michael J. and Hilliges,
            Otmar},
  booktitle = {Proceedings IEEE Conference on Computer Vision and Pattern
               Recognition (CVPR)},
  year = {2023}
}
```
