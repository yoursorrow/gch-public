# GCH (Gmod Content Helper)

GCH (Gmod Content Helper) is a tool designed to assist with the preparation of Garry's Mod addons for compression using GAC (Gmod Addon Compressor). GCH provides utilities and functions to help optimize and organize addon files before compressing them with GAC. This tool simply accelerates the process using GMAD, which was created by Facepunch.

### Tutorial: Using GCH for Garry's Mod Content Packs

### Video Tutorial: GCH - Gmod Content Helper

If you prefer visual instructions, you can watch this comprehensive [video tutorial](https://www.youtube.com/watch?v=WX4Z8od8zgE&feature=youtu.be) on using GCH (Gmod Content Helper) for Garry's Mod.

## Prerequisites

Before you start using GCH (Garry's Mod Content Helper) for packaging your Garry's Mod addons, make sure you have the following:

- GCH installed on your system.
- .gma files of the addons you want to work with. If you don't have any .gma files, you can obtain them from either the Garry's Mod workshop folder or the legacy addons folder.

### Getting Started

1. Create a folder on your system where you want to work with your addons.
2. Copy the .gma files you want to extract and optimize into this folder.

### Extracting Addons

1. Open the GCH tool and navigate to the folder where you placed your .gma files.
2. Click on the "Open Directory" button in GCH. If you encounter an error, it may indicate that there are too many files to read.
3. Once the directory is opened successfully, click on the "Extract" button in GCH.
4. GCH will extract the contents of the .gma files into the same folder.

### Compressing Addons with GAC (Garry's Mod Addon Compressor)

1. Download and open GAC (Gmod Addon Compressor) from [here](https://github.com/Shark-vil/GmodAddonCompressor/releases/tag/v2.0.4).
2. In GAC, select the folder where you extracted the addon contents using GCH.
3. GAC will compress the addons into the final format.

### Repacking Compressed Addons

To repack the compressed addons, follow these steps:

1. Once GAC has finished compressing your addons, go back to GCH.
2. In GCH, click on the "Pack" button.
3. GCH will automatically repack the compressed addons into .gma files, making them ready for use.

### Creating the Content Pack

To create the content pack, follow these steps:

1. In GCH, click on the "Create" button.
2. GCH will take a moment to load, depending on the size of the content. During this process, take note of any file conflictions GCH alerts you about.
3. Once the creation process is complete, you will find two folders generated by GCH:
   - The "release" folder contains the raw content pack information, which is not in .gma format.
   - The "bin" folder contains the "gchcontentpack.gma" file, which you will upload to the workshop.


### Additional Notes

- **Experimental Features**: GCH offers experimental features that you can enable by going to Options and clicking on "Experimental Features." Enabling this feature makes the "Create" button available. When using this feature, ensure that your extracted folder is still present and click on "Create." It is highly recommended to keep the file size below 900 Megabytes to avoid potential issues with the GMAD tool.

- **Asynchronous merging**: This feature is a full release in 2.0, unlike extraction. This does see a decent speed improvement over its V1 counterpart, so it stays.

- **Debugging GMAD Errors**: If you encounter issues related to GMAD (Garry's Mod Addon Creator), you can uncomment specific lines in the GCH code to enable error debugging. To do this, locate the following lines in the code:

    ```csharp
    /* This is for debugging errors in GMAD, not GCH !!!!!!!!! THIS NEEDS TO BE CHANGED !!!!!!!!!!! IT IS DONE A DIFFERENT WAY NOW
        -- process.ErrorDataReceived += Process_ErrorDataReceived;
        -- process.OutputDataReceived += Process_OutputDataReceived;
    */
    ```

    Remove the `/*` and `*/` around these lines to uncomment them. This will provide more detailed error information in case of GMAD-related problems.

- **Message Box Prompt**: In contrast to GCH1, GCH2's logging system is actually taken advantage of and is used quite frequently. The only time you should see messageboxes is if there was a completed action that needs immediate attention, or a file confliction (maybe)

- **Addon.json File Replacement**: GCH creates an addon.json file for each extracted .gma file. If an addon.json file already exists, GCH replaces it with the newly generated one to ensure it remains up to date with any changes made during the optimization process.
