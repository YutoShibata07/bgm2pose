# [IEEE OJSP 2026] BGM2Pose: Active 3D Human Pose Estimation with Non-Stationary Sounds

[Yuto Shibata](https://yutoshibata07.github.io/YutoShibata/)<sup>1</sup>,
[Yusuke Oumi](https://oumi03.github.io/)<sup>1</sup>,
[Go Irie](https://www.rs.tus.ac.jp/prmi/)<sup>1,2</sup>,
[Akisato Kimura](https://akisatok.tech/)<sup>3</sup>,
[Yoshimitsu Aoki](https://aoki-medialab.jp/home-en/)<sup>1</sup>,
[Mariko Isogawa](https://isogawa.ics.keio.ac.jp/)<sup>1,4</sup>

<sup>1</sup>Keio University &nbsp; <sup>2</sup>Tokyo University of Science &nbsp; <sup>3</sup>NTT, Inc. &nbsp; <sup>4</sup>JST PRESTO

**IEEE Open Journal of Signal Processing, Vol. 7, 2026**

[Project Page](https://yutoshibata07.github.io/bgm2pose-project-page/) |
[Paper](https://ieeexplore.ieee.org/document/11570037/) |
[arXiv](https://arxiv.org/abs/2503.00389) |
[AMPL Dataset](https://ieee-dataport.org/documents/acoustic-music-based-pose-learning-ampl)

![BGM2Pose overview](https://raw.githubusercontent.com/YutoShibata07/bgm2pose-project-page/main/static/images/teaser.png)

BGM2Pose estimates 3D human poses using ordinary background music as the active sensing signal.
Two off-the-shelf speakers play the music, a single ambisonics microphone records the room, and the
model predicts the pose from the recording and the playback track. No chirp signals, no cameras.

## News

- **2026.09** &nbsp; As an IEEE OJSP paper, BGM2Pose will be given as an oral presentation in the Spotlight session
  at IEEE ICIP 2026 in Tampere, Finland (Mon, Sep 14, 11:30–12:00, *3D Scene Estimation and Representation 1*, Room Maestro).
- **2026.06** &nbsp; BGM2Pose has been accepted to the IEEE Open Journal of Signal Processing.

## Code

The training and evaluation code will be released in this repository by the end of September 2026.

## Dataset

The AMPL (Acoustic Music-based Pose Learning) dataset is available on
[IEEE DataPort](https://ieee-dataport.org/documents/acoustic-music-based-pose-learning-ampl)
(DOI: [10.21227/ryz7-b544](https://doi.org/10.21227/ryz7-b544); login required).
It was recorded in a classroom with background noise and reverberation, using four BGM tracks
(ARNOR, Cirrus, MANTRA: ambient; Kurina blues: jazz) and a 16-camera motion capture system.

### Download

Download `ampl.zip` from IEEE DataPort and unzip it into the `pose_estimation/` directory of this repository.
The archive contains a single folder, `dataset_spec_2400/`, so the data ends up in `pose_estimation/dataset_spec_2400/`.

```bash
unzip ampl.zip -d pose_estimation/
```

The paths in `music_intensity.csv` are relative to `pose_estimation/` (e.g. `./dataset_spec_2400/music_with_intensity/...`),
so keep this layout when running the code.

### Contents

The dataset consists of 25,354 samples. Each sample covers a 0.6 s window and pairs preprocessed acoustic
features with the ground-truth 3D poses captured by motion capture. Raw microphone recordings and the
original music tracks are not included.

```
pose_estimation/dataset_spec_2400/
├── music_intensity.csv
└── music_with_intensity/
    ├── subject_<s>_<track>_<idx>_0.6_music_intensity.npy   # acoustic features
    └── joint_pos_subject_<s>_<track>_<idx>_0.6.npy         # 3D poses
```

- **Acoustic features** (`*_music_intensity.npy`): log-mel spectrograms combined with intensity vectors,
  stored as `float32` arrays of shape `(15, 128, 12)` (channels × mel bins × frames at 20 FPS).
- **3D poses** (`joint_pos_*.npy`): `float32` arrays of shape `(12, 63)`, i.e. 12 frames of 21 joints in 3D.
  Poses are normalized so that the spine–hip distance is 1.
- **Index** (`music_intensity.csv`): one row per sample, linking the feature file (`sound_path`) to its pose file
  (`joint_path`), together with the subject (`testee`) and the music track (`music_type`).

The tracks appear in file names as `arnor`, `cirrus`, `mantron` (MANTRA) and `jazz` (Kurina blues).

### Subject IDs

Due to missing or corrupted motion capture data, the subject IDs in the dataset files differ from those in the paper.
Use the following mapping when comparing with the paper.

| Subject ID in files | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|---|---|---|---|---|---|---|---|---|---|---|
| Subject ID in paper | 1 | 9 | 6 | not used | 7 | 8 | 2 | 3 | 4 | 5 |

## TODO

- [x] Release the AMPL dataset
- [x] Launch the [project page](https://yutoshibata07.github.io/bgm2pose-project-page/)
- [ ] Release training and evaluation code (September 2026)

## Citation

```bibtex
@article{shibata2026bgm2pose,
  title   = {{BGM2Pose}: Active {3D} Human Pose Estimation With Non-Stationary Sounds},
  author  = {Shibata, Yuto and Oumi, Yusuke and Irie, Go and Kimura, Akisato and Aoki, Yoshimitsu and Isogawa, Mariko},
  journal = {IEEE Open Journal of Signal Processing},
  volume  = {7},
  pages   = {790--799},
  year    = {2026},
  doi     = {10.1109/OJSP.2026.3705347}
}
```
