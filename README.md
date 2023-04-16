# hemanup
I want to upscale 80s cartoons.

In one day's testing, I determined that Topaz Video AI (pirated) is a good way to denoise videos.

Looking at the [upscale wiki](https://upscale.wiki/wiki/Model_Database) it seems that ESRGAN is the way to go. 
Looking at the github repo, they direct us toward [Real-SRGAN](https://github.com/xinntao/Real-ESRGAN). I'll investigate that next.

## Real-ESRGAN
* clone the repo
* I tried using venv, then it turns out one of the packages can't work on python 3.11.2, then it said to use miniconda.
* install miniconda, it's cool.
* Short story: it works.
<p align="center">
<img src="images/test-original.png"/>&nbsp;&nbsp;<img src="images/test-upscale.png">
</p>

## running old filters
So for the older ESRGAN model, there's a [big list of models](https://upscale.wiki/wiki/Model_Database) at the upscale wiki, but they recommend running [chaiNNer](https://github.com/chaiNNer-org/chaiNNer), which is rad, but unusably slow, and maxes out on memory for some reason. So I wish I could use it with the script from before.

In particular I'd like to try the [ToonVHS](https://upscale.wiki/wiki/Model_Database#VHS_Tapes) model.

I'll try to make `Real-ESRGAN/inference_realesrgan_video.py` run with the old model.

The ESRGAN can be represented by [this code](https://github.com/xinntao/ESRGAN/blob/master/RRDBNet_arch.py). There's also a [much more complex version](https://github.com/chaiNNer-org/chaiNNer/blob/main/backend/src/nodes/impl/pytorch/architecture/RRDB.py), but I like the first one better. Can I just use that?

## Pirating topaz labs
I downloaded it from [ianon.app](https://ianon.app). Now it's running, gave me a preview. Looked good. I'm using the "Artemis Denoise/Sharpen" with "Strong Halo" setting, and a "Progressive" video type. It's faster than `Real-ESRGAN` -- generating the clean version at about 22.5fps.
# references
## papers
* [ESRGAN: Enhanced Super-Resolution Generative Adversarial Networks](https://arxiv.org/abs/1809.00219)
* [Deep Learning on Image Denoising: An overview](https://arxiv.org/abs/1912.13171)
* [Recent progress in image denoising: A training strategy perspective](https://ietresearch.onlinelibrary.wiley.com/doi/full/10.1049/ipr2.12748)
* [Lightweight Video Denoising using Aggregated Shifted Window Attention](https://openaccess.thecvf.com/content/WACV2023/papers/Lindner_Lightweight_Video_Denoising_Using_Aggregated_Shifted_Window_Attention_WACV_2023_paper.pdf)

## hugging face

## youtube

## github
* [ViDeNN](https://github.com/clausmichele/ViDeNN)
  * [ViDeNN: Deep Blind Video Denoising](https://openaccess.thecvf.com/content_CVPRW_2019/papers/NTIRE/Claus_ViDeNN_Deep_Blind_Video_Denoising_CVPRW_2019_paper.pdf)

