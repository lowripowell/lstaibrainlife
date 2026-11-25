<h1 align="center">LST-AI</h1>

<p align="center">
  Segments multiple sclerosis white matter lesions from T1-weighted and FLAIR images with LST-AI and outputs lesion masks.
</p>

<p align="center">
  <a href="https://github.com/brainlife/abcd-spec"><img src="https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg" alt="ABCD Spec v1.1"></a>
  <a href="https://doi.org/10.25663/brainlife.app.886"><img src="https://img.shields.io/badge/Brainlife-brainlife.app.886-blue.svg" alt="Run on brainlife.io"></a>
</p>

## At a glance

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Segments multiple sclerosis white matter lesions from T1-weighted and FLAIR images with LST-AI and outputs lesion masks.**

Thin wrapper that runs the LST-AI command (lst --t1 --flair --output) without modifying it. Use it for MS lesion segmentation when you have T1w and FLAIR of the same subject. The main script reads inputs from config.json keys that do not match the registered keys and calls lst without a container, so the App may not run as registered.

| | |
|---|---|
| **Inputs** | `neuro/anat/t1w` · `neuro/anat/flair` |
| **Outputs** | `neuro/mask` · `raw` |
| **Run it** | [doi.org/10.25663/brainlife.app.886](https://doi.org/10.25663/brainlife.app.886) |

#### Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `T1_input` | `neuro/anat/t1w` | yes | T1-weighted MRI |
| `FLAIR_input` | `neuro/anat/flair` | yes | FLAIR MRI |

#### Outputs

| Output | Datatype | Description |
|---|---|---|
| `masks` | `neuro/mask` | LST-AI segmentation masks (annotated and unannotated) |
| `stats` | `raw` |  |

<!-- brainlife-app:end -->

## Running the App

### On brainlife.io

Open the App at [doi.org/10.25663/brainlife.app.886](https://doi.org/10.25663/brainlife.app.886), choose `neuro/anat/t1w`, `neuro/anat/flair` from your project and press **Execute**. The results are saved to your project as `neuro/mask`, `raw`.

### Locally

You need [`jq`](https://jqlang.github.io/jq/).

1. Clone this repository.
2. Create `config.json` with the paths to your inputs and the parameters:

   ```json
   {
       "t1": "/path/to/T1_input/t1",
       "flair": "/path/to/FLAIR_input/flair"
   }
   ```

3. Run `./main`.

## Citing

If you use this App, please cite it, the software it builds on and brainlife.io:

- LST-AI. brainlife.io App. [doi:10.25663/brainlife.app.886](https://doi.org/10.25663/brainlife.app.886)
- Hayashi S, Caron BA, Heinsfeld AS, et al. brainlife.io: a decentralized and open-source cloud platform to support neuroscience research. *Nature Methods* 21:809–813 (2024). [doi:10.1038/s41592-024-02237-2](https://doi.org/10.1038/s41592-024-02237-2)
- Avesani P, McPherson B, Hayashi S, et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. *Scientific Data* 6:69 (2019). [doi:10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)

## Authors

Maintained by [@lowripowell](https://github.com/lowripowell).
