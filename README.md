
Who I am?  
[drmbt.com](drmbt.com)   
[@drmbt](instagram.com/drmbt)   
_![Vincent](/assets/Vincent-AI-browneyes.png)__

Vincent Naples  

artist and creative technoligist originally from Chicago working with a broad swathe of digital mediums, including projection and light, VJ and interaction design protocols, TouchDesigner, and most recently AI image generation using a variety of models and text2image protocols  

___
Am I an expert?  
___
not really.  

but I have spent a fair amount of time experimenting as a lay user, and as an artist for whom some of the tasks of content creation can now be done by AI models

I recently had the first opportunity to use AI in a commercial setting when projection mapping a building, and have been imagining and experimenting with workflows for incorporating these tools into my existing workflows

[OCELOT_SF](https://photos.app.goo.gl/9e3YeFoEEYBDidJp6)

___
Early days in the space = developers and researchers in local dependancy hell

next came colab notebooks distributed via twitter and patreon making accessible interfaces that didnt require coding or specialized hardware

We are now at the appified / micro service stage of this technology, where lay users can work with the tools without any prior experience or coding background, either locally through accessible UIs or via cloud services and APIs

___
What is text 2 image?  
![avocado](/assets/avocado-chair.png)  
using descriptive strings of words, AI image generation models create images derived from sophisticated data models trained on massive data sets 
___
How it works:  

**CLIP** (**C**ontrastive **L**anguage-**I**mage **P**re-training) from open AI tokenizes a string input and maps the prompt into representational space   

Next, a model called the **prior** maps the text encoding to a corresponding **image** **encoding** that captures the semantic information of the prompt contained in the text encoding.  

Finally, an **image decoder** stochastically generates an image which is a visual manifestation of this semantic information.  

https://www.assemblyai.com/blog/how-dall-e-2-actually-works/  

![diffusion.png](/assets/diffusion.png)  

___


What is a diffusion model?  

[https://scale.com/guides/diffusion-models-guide](https://scale.com/guides/diffusion-models-guide) 
[https://lilianweng.github.io/posts/2. 21-07-11-diffusion-models/](https://lilianweng.github.io/posts/2021-07-11-diffusion-models/) 
![generative-overview](/assets/generative-overview.png)  

---
a very incomplete list of some ways people are using text2image in mid 2022:

Stable Diffusion - [DreamStudio](https://beta.dreamstudio.ai/dream) official web app from Stability AI, currently open model
[Dalle-2](https://openai.com/dall-e-2/) closed source paid token model, cloud based with API
[Wombo.ai](https://www.wombo.ai/) Dream app, cloud based freemium model
[Starry AI](https://www.starryai.com/) local app, cloud based rendering, demo credits, paid token model
[Craiyon](https://www.craiyon.com/) cloud based, free, queue'd renders, lots of ads, begs for donations
[Runway ML](https://runwayml.com/training/) suite of ML tools for codelessly training ML models

private Discord servers
    - [Midjourney](https://www.midjourney.com/) discord microservice for text2image with some free tokens, paid subscription
    - [Eden](https://www.edenai.co/) not yet public suite of ML tools with API for combining pipelines: [abraham.ai](abraham.ai)
Colab Notebooks
    - [Deforum video notebook](https://colab.research.google.com/github/deforum/stable-diffusion/blob/main/Deforum_Stable_Diffusion.ipynb#scrollTo=qH74gBWDd2oq) probably most widely used notebook for video frame animation
    - [Hugging Face](https://colab.research.google.com/github/huggingface/notebooks/blob/main/diffusers/stable_diffusion.ipynb) official SD notebook for image creation
local
    - SD implemention win/linux [example](https://www.youtube.com/watch?v=6MeJKnbv1ts)
    - [NMKD](https://nmkd.itch.io/t2i-gui) 
    - [Diffusion Bee on mac](https://diffusionbee.com/)
    - [Draw Things on iOS](https://apps.apple.com/us/app/draw-things-ai-generation/id6444050820)
    - [SD UI LINUX](https://stable-diffusion-ui.github.io/docs/installation/) 
    - [AUTOMATIC1111](https://github.com/AUTOMATIC1111/stable-diffusion-webui/)
    - [INVOKE AI](https://github.com/invoke-ai/InvokeAI)

prompt engineering / SD resources:
    - [Lexica.art](Lexica.art ) SD search engine
    - [arthub.ai](https://arthub.ai/)
    - [Visual Prompt Builder](https://tools.saxifrage.xyz/prompt)
	- [diffusiondb](https://diffusiondb.com/) list of SD tools, UIs, forks etc
___
How do I use SD?    

. latforms:   
	- Eden discord server  
	- NMKD windows GUI  
	- Automatic1111 and Invoke browser UIs
	- tested  diffusionbee to test macOS SD  
	- played a bit with Draw Things to test iOS capabilities  
	- Colab deforum notebook, or thru [dotsimulate tools](instagram.com/dotsimulatre)  

techniques:   
	- image generation  
	- frame blend animations  
	- image2image with seed (projection mapping)  
	- inpainting: select region of interest and generate fill  
	- [outpainting](https://openai.com/blog/dall-e-introducing-outpainting/) expand original composition by imagining what is outside of frame  
___
let's talk about prompt engineering   

![](/assets/prompt-grid.jpeg)

https://vivian-liu.com/text2image
___
Let's make something with NMKD  

text2image basic parameters:  
	- prompt: text string used as guidance input for diffusion model  
		- what is prompt engineering?  
	- size/ratio  

advanced parameters:  
	- init scale (for image2image seed)  
	- seed (deterministic starting point for random noise generation. same prompt +same seed = same image)  
	- CFG scale = weight of prompt's impact on the generated image  
	- [tileable](https://replicate.com/tommoore515/material_stable_diffusion) = circular convolution projects edges into a torus, creating perfectly tiled images   
___

[what is a colab notebook](https://research.google.com/colaboratory/faq.html#:~:text=Colaboratory%2C%20or%20%E2%80%9CColab%E2%80%9D%20for,learning%2C%20data%20analysis%20and%20education.)? 

Colaboratory, or “Colab” for short, is a product from Google Research. Colab allows anybody to write and execute arbitrary python code through the browser, and is especially well suited to machine learning, data analysis and education. More technically, Colab is a hosted Jupyter notebook service that requires no setup to use, while providing access free of charge to computing resources including GPUs.

___
Let's make something with [Deforum video notebook](https://colab.research.google.com/github/deforum/stable-diffusion/blob/main/Deforum_Stable_Diffusion.ipynb#scrollTo=qH74gBWDd2oq) 

[Intro to Deforum notebook](https://www.youtube.com/watch?v=w_sxuDMt_V0) shoutout to dotsimulate  

Deforum is a colab that uses SD and a model called Midas. that generates a depth map from an input image. After the first image is created, that frame is fed back through the model along with the depth map to create frame animations that appear to have camera motion. Coupled with keyframed text prompts, this allows users to create motion sequences using text prompts  

relevant parameters:  
	- settings: 2d vs 3d  
	- max frames   
	- set border to wrap  
	- define camera motion  
	- padding to reflection  
	- resolution  
	- seed  
	- sampler  
	- scale    

this will take awhile to render, let's let that go for awhile  

___
Ways I've been using these tools:  
	- image generation  
	- stylizing input images  
	- architectural projection mapping  
	- TouchDesigner/VJ tools  
___
[LOVE.STADT](https://photos.app.goo.gl/sPqkMDdL6JdrxjDy6) process   
	- NMKD gui   
	- exploring prompts assembled from trial and error, lexica.art  
	- finding seeds I like  
	- batching all of the CFG scale weights  
	- small iterations, a whole lot of content  
	- curating the good shit  

4105893191  

body horror, female model, close up portrait, epic light, melting liquid, acrylic painting, abstract, in glass and black latex fluid, hyperrealistic, 3d sculpture, bokeh, long exposure, art noveau, artistic sketch,  film still, body paint, shallow depth of field, dithering, animation style of Alberto Mielgo

___
[Stylized Hermana](https://photos.app.goo.gl/kdoQTP19McN8r1VJ7)  
using prompts and init image to generate stylized output  
experiments with init and CFG scale to find a sweet spot.  
Init between .25 and .45 seems strong   

styles:  
Horror Movie Chucky doll (with in painting)  
Baroque painting  
Manga / Anime / Dragonball Z  
Andy Warhol Screenprint  
Superficially Beautiful pencil drawing  
Goth  
___
How I use this with projection / VJing:  
	- init image of perspective corrected facade 
	- [tileable](https://replicate.com/tommoore515/material_stable_diffusion) images  
	- Lyell Hintz depth map fx  
___
TouchDesigner and AI tools  
	- TD EDEN to generate images from prompts remotely
	- prompt engineering assembler and tools  
	- tileable noise substitute with circular convolution images  


