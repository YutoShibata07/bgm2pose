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

The AMPL dataset (4+ hours of synchronized music, recorded audio and motion capture from 9 subjects)
is already available on [IEEE DataPort](https://ieee-dataport.org/documents/acoustic-music-based-pose-learning-ampl).

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
