# ARCTIC download contents

This inference-benchmark fork retains the official download, checksum, and
unpack utilities only. See the repository root `README.md` for credentials and
commands, and [`data_doc.md`](data_doc.md) for the upstream data schema.

Available downloads:

- `download_images.sh`: full-resolution allocentric and egocentric images
- `download_cropped_images.sh`: cropped images for smoke tests
- `download_misc.sh`: camera, subject, and object metadata
- `download_splits.sh`: processed annotations and split definitions
- `download_body_models.sh`: licensed MANO and SMPL-X model files
- `download_mocap.sh`: optional motion-capture data
- `download_dry_run.sh`: small credential and pipeline check

For AKAGI exp003, use full-resolution images, metadata, splits, and body
models. Cropped images are limited to smoke tests. Baseline weights, extracted
features, preprocessing, rendering, training, and official benchmark code are
outside this fork's scope.
