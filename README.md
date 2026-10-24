# EVE for OpenCode beta

EVE adds a local Qwen 27B option to your existing OpenCode setup. The customer
image is built for NVIDIA GPUs and runs through vLLM. 

## Get access

1. Fill out the [EVE beta form](https://tally.so/r/Dq2q75).
2. The form completion page shows your unique beta code, the image repository,
   and a release unlock code. Copy those values before leaving the page.
3. Download `eve-beta-0.2.2.zip` from this repository's Releases page.
4. Extract it and follow `START_HERE.md` inside to unlock and install.

The public ZIP contains an encrypted, signed release manifest. No private
handoff ZIP or email is required. The form unlock code is shared for this release.
The beta code helps us associate optional usage reports with your signup. It
does not control activation. Once installed, EVE can run without contacting us.

You need suitable NVIDIA GPU memory, Docker with GPU support, Python 3.10+,
Node 22+, OpenCode 1.18.x, an existing OpenCode JSON configuration, and a Git
project with at least one commit. Model weights download on first installation.

Usage reporting is optional and on by default. It sends a beta code, random
installation ID, event ID, completion time and version. It sends no prompts,
responses, code, filenames or email addresses. Add `--telemetry-off` when
installing to disable it. Google receives normal network connection metadata.

Publisher public-key SHA-256 fingerprint (compare this with your invitation):

```text
bb479b776acd32a8644b41626feb19b08b81aad3abb93b6092a88338e2250f00
```

The ZIP's SHA-256 is listed in the GitHub Release description. Verify
it before extracting. Source code for EVE's vectors is not included here.

## Choosing a different Qwen3.8-27B checkpoint

Release 0.2.2 defaults to the pinned INT4 checkpoint. To choose another
compatible Hugging Face checkpoint, supply `--model-id OWNER/REPO` and an exact
40-character `--model-revision` commit when running `beta_setup.py`. The worker
checks the Qwen3.8-27B architecture before downloading weights and lets vLLM
read the quantization method from the checkpoint. Other checkpoints may need
more GPU memory or use unsupported formats, and EVE quality must be rechecked
on each model. Do not mix this ZIP with the older 0.2.1 image or installer.
