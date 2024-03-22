
# Tips in General

https://github.com/VAST-AI-Research/TripoSR is the current state-of-the-art for high-quality meshes, and the only algorithm for which one won't encounter the Janus problem.

Specific tips for threestudio are below.

## Tips for threestudio 

threestudio is a unified framework for 3D content creation from text prompts, single images, and few-shot images, by lifting 2D text-to-image generation models.

### Scripts

The best available model, quality-wise, is ProlificDreamer, which can be run 

```sh
python launch.py --config configs/prolificdreamer_hd.yaml --train --gpu 0 system.prompt_processor.prompt="a marble sculpture by Michelangelo" system.guidance.grad_clip=[0,0.5,2.0,10000] system.prompt_processor.use_perp_neg=true
```

### Scene Generation

Scene generation requires more VRAM than other methods due to non-sparseness of the output. Because of that, one can use the settings provided that reduce the requirements for prolificdreamer to 40GB VRAM.