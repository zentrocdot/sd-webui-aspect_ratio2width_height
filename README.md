
# Extension for the AUTOMATIC1111 Web UI
#### sd-webui-aspect_ratio2width_height Version 0.0.0.1

<p align="justify">sd-webui-aspect_ratio2width_height is an <i>Extension</i> for the <a href="https://github.com/AUTOMATIC1111/stable-diffusion-webui">AUTOMATIC1111/stable-diffusion-webui</a>, which is adding a dropdown menu to the web UI for the selection of predefined <i>aspect ratios</i>.</p>

---

# Preface

The aspect ratio has always been an important aspect of art over time. Since I could not find any suitable tools that did what I wanted, I tried to programme my own Extension for AUTOMATIC1111. Since that worked out successfully, I went on to programme interesting aspects around the topic of aspect ratios.

# Goal

<p align="justify">The aim was to develop an extension that creates width and height from any given aspect ratio. It should also be possible to transfer the calculated data to the web UI.</p>

# What the Extension Does

After installation one will find panel within the web UI which looks like the next one when it is opened.

<a target="_blank" href=""><img src="./images/image_aspect_ratio_width_height.png" alt="button panel"></a>

One can enter an aspect ratio like 6:5 or 5:6 in the text field. Using the Calculate button Width and Height are calculated. Using the Apply button one can use the calculated values for Width and Height in the web UI.

I added two features, to have more control over the calculation. As everybody knows a resolution must be an integer number and not a floating point number. By the radio button Rounding rounding of the values can be enforced. By the radio button Exact Calculation an exact calculation will be performed.

Let me explain what exact calculation means using an example. Let's say that we want to use an aspect ratio of 6:5. The regular calculation leads to a resolution of 614.4 x 512 pixel. An exact calculation leads to a resolution of 624 x 520 pixel. The first one needs to be rounded to be meaningful usable in the image generation.

# Development and Test Environment

The <i>Extension</i> was devolped and tested under Linux using the web UI AUTOMATIC111 with following specification:

* API: v1.10.0
* Python: 3.10.14
* torch: 2.1.2+cu121
* xformers: 0.0.23.post1
* gradio: 3.41.2

# Unresolved Question

<p align="justify">The data transfer of the calculated values for width and height is not as straightforward as I would expect. It works and I understand why it works, but it's not elegant.</p>

# Challenge

<p align="justify">Especially with this <i>Extension</i> I had to struggle a lot with the functionality of <i>gradio</i> in my current version. Many things that should work according to the documentation of <i>gradio</i> did not work or only worked to a limited extent with sometimes bizarre results. I had to play tricks to create the interface in its present form.</p>

# Reference

[1] https://github.com/AUTOMATIC1111/stable-diffusion-webui

[2] https://github.com/AUTOMATIC1111/stable-diffusion-webui-extensions
