# Rembg

[![Downloads](https://img.shields.io/pypi/dm/rembg.svg)](https://img.shields.io/pypi/dm/rembg.svg)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://img.shields.io/badge/License-MIT-blue.svg)
[![Hugging Face Spaces](https://img.shields.io/badge/🤗%20Hugging%20Face-Spaces-blue)](https://huggingface.co/spaces/KenjieDec/RemBG)
[![Streamlit App](https://img.shields.io/badge/🎈%20Streamlit%20Community-Cloud-blue)](https://bgremoval.streamlit.app/)

Rembg is a tool to remove images background.

**If this project has helped you, please consider making a [donation](https://www.buymeacoffee.com/danielgatis).**

## Requirements

```text
python: >3.7, <3.13
```

# Background Removal Tool Setup and Usage Guide

This guide provides step-by-step instructions on how to set up and use the background removal tool using the `rembg` Python package. It includes installation instructions, creating necessary files, and configuring a right-click context menu action in the file manager.

## Environment Setup

1. Ensure you have Python installed on your system. You can download and install Python from the [official Python website](https://www.python.org/).

2. Create a virtual environment to install and manage Python packages:

    ```bash
    python3 -m venv /path/to/venv
    ```

3. Activate the virtual environment:

    ```bash
    source /path/to/venv/bin/activate
    ```

## Installing Dependencies

1. Install the `rembg` Python package in the virtual environment:

    ```bash
    pip install rembg
    ```

## Creating Files

1. Create the script file `remove_background.sh` to automate the background removal process:

    ```bash
    touch remove_background.sh
    ```

2. Open the script file in a text editor and paste the following script:

    ```bash
    #!/bin/bash

    # Activate the virtual environment
    source /path/to/venv/bin/activate

    # Run rembg on the selected image file
    rembg "$1" "${1%.*}_no_bg.png"

    # Deactivate the virtual environment
    deactivate
    ```

3. Make the script executable:

    ```bash
    chmod +x remove_background.sh
    ```

## Configuring Right-click Context Menu Action

1. Create a `.desktop` file for the right-click context menu action:

    ```bash
    touch /usr/share/nemo/actions/remove_background.nemo_action.desktop
    ```

2. Open the `.desktop` file in a text editor and paste the following content:

    ```
    [Nemo Action]
    Name=Remove Background
    Comment=Remove the background from selected image(s)
    Exec=/path/to/remove_background.sh %F
    Icon-Name=applications-graphics
    Selection=s
    Extensions=png;jpg;jpeg;gif;
    ```

3. Save the `.desktop` file.

## Usage

1. To remove the background from a single image file, right-click on the image file in the file manager and select "Remove Background" from the context menu.

2. To remove the background from multiple image files, select the desired files, right-click, and choose "Remove Background".

3. The background removal process will be automatically executed, and the resulting images will be saved with "_no_bg.png" suffix in the same directory as the original images.

4. You can customize the script and `.desktop` file according to your preferences and requirements.



## Some video tutorials

- <https://www.youtube.com/watch?v=3xqwpXjxyMQ>
- <https://www.youtube.com/watch?v=dFKRGXdkGJU>
- <https://www.youtube.com/watch?v=Ai-BS_T7yjE>
- <https://www.youtube.com/watch?v=D7W-C0urVcQ>

## References

- <https://arxiv.org/pdf/2005.09007.pdf>
- <https://github.com/NathanUA/U-2-Net>
- <https://github.com/pymatting/pymatting>

## Buy me a coffee

Liked some of my work? Buy me a coffee (or more likely a beer)

<a href="https://www.buymeacoffee.com/danielgatis" target="_blank"><img src="https://bmc-cdn.nyc3.digitaloceanspaces.com/BMC-button-images/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;"></a> <!-- markdownlint-disable MD033 -->

## License

Copyright (c) 2020-present [Daniel Gatis](https://github.com/danielgatis)

Licensed under [MIT License](./LICENSE.txt)
