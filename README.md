# Vision Transformer Visualization: What Neurons Tell and How Neurons Behave?
This is the official implementation of ViT visualization tool

![image](./fig/visual_diagram.PNG)

## Prepare environment
The anaconda env file is `vit_visualize.yml`
To create the environment, please install `annaconda` first and then run:

`conda env create -f vit_visualize.yml`

To make the jupyter notebook could load the environment, run:

`python -m ipykernel install --user --name=vit_visual`

During this analysis we use model [Vision Transformer](https://github.com/google-research/vision_transformer) with version `ViT-B16/224`. To download the pretrain-weights of aforementioned model over `ImageNet21k + ImageNet2012` and save to `weights` folder, we should run the below bash commands:

```{bash}
mkdir -p weights
wget -O weights/ViT-B_16-224.npz /tmp/Ubuntu.iso https://storage.googleapis.com/vit_models/imagenet21k+imagenet2012/ViT-B_16-224.npz
```

## What Neurons Tell?

This [ViT_neuron_visualization](ViT_neuron_visualization.ipynb) notebook file includes the code we analyze the neuron's view that includes the below items according to the sector `What Neurons Tell` of the paper:

* Visualize filters and views of a specific input patche at 0'th layer:


<center><img src="./fig/layer0_embedding_row.png" alt="View of a patch" width="80%"/></center>

* Comparing the views of different filters. Afterward, concluding that each filter is good for a specific group images but not good for the others group images.

<center><img src="./fig/layer0_good_bad_filters.png" alt="Comparing view of embedding" width="80%"/></center>


* Create a global view at the higher layers and compare the global views corresponding with different patches.

<center><img src="./fig/layer_high_object_non_object.png" alt="Global view over layers" width="60%"/></center>

* Analyze the views of salient, non-salient, and random occlusion cases over the depth-level layers.

<center><img src="./fig/all_drops.png" alt="Occlusion comparison" width="60%"/></center>

## How Neurons Behave?
We implement the code the generate clustering behavior of embeddings in [ViT_embedding_visualization](ViT_embedding_visualization.ipynb) with full instruction to reproduce the result

![image](./fig/tsne_dog_cat.png)

![image](./fig/tsne_multi_objects.png)

