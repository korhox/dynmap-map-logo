# Screenshot & demo
View screenshot here: https://i.korho.fi/i/1b1b248b3

View demo here: https://kartta.flosmine.fi/

# Jump to
1. [Notes](https://github.com/korhox/dynmap-map-logo#notes)
2. [Adding logo with link and hover effect](https://github.com/korhox/dynmap-map-logo#adding-logo-with-link-and-hover-effect)
3. [Adding logo without linking and hover effect](https://github.com/korhox/dynmap-map-logo#adding-logo-without-linking-and-hover-effect)
4. [Last words](https://github.com/korhox/dynmap-map-logo#last-words)

# 1. Notes
1. This tip assumes that you are using and installed [Dynmap](https://github.com/webbukkit/dynmap).
2. If you are on linux/mac os or using hosting provider, you do not need to worry about directory paths in this tip. If you are on windows, note that your file system is using backslashes instead of normal slashes, so you need to navigate to file with `\path\to\file\`.

# 2. Adding logo with link and hover effect
Clicking image will open new window to defined site.
## Step 1
Open `index.html` in your server directory `/plugins/dynmap/web/`

**Find:**
```
</head>
```

**Replace it with:**
```
    <style>
        .korhoLogo img {
            position: absolute;
            bottom: 20px;
            right: 40px;
            max-width: 210px;
            transition:0.2s ease-in-out opacity;
            opacity:0.9;
        }
    
        .korhoLogo img:hover {
            opacity:0.4;
            cursor: pointer;
        }
    </style>
</head>
```
## Step 2
In same index.html file
**Find:**
```
<div id="mcmap"></div>
```

**Replace it with:**
```
<div id="mcmap"></div>
<div class="korhoLogo">
    <img onclick="window.location='YOUR-URL-HERE'" src="/images/korho-logo.png">
</div>
```

In last replace, you need to replace `YOUR-URL-HERE` with URL, where you want to send your visitors when image is clicked.

## Step 3
Upload your logo to `/plugins/dynmap/web/images/` with name korho-logo.png. Recommended image resolution is 420x150. Image height can varie with your logo style. Image can be bigger or smaller, but it will impact the look of it. You can change the width (and therefore in height as well) of image with CSS changing value of `max-width` defined in CSS (within <style>-tags).
  
# 3. Adding logo without linking and hover effect
Image is just always there and really does nothing.

## Step 1
Open `index.html` in your server directory `/plugins/dynmap/web/`

**Find:**
```
</head>
```

**Replace it with:**
```
    <style>
        .korhoLogo img {
            position: absolute;
            bottom: 20px;
            right: 40px;
            max-width: 210px;
            transition:0.2s ease-in-out opacity;
            opacity:0.9;
        }
    </style>
</head>
```
## Step 2
In same index.html file

**Find:**
```
<div id="mcmap"></div>
```

**Replace it with:**
```
<div id="mcmap"></div>
<div class="korhoLogo">
    <img src="/images/korho-logo.png">
</div>
```

## Step 3
Upload your logo to `/plugins/dynmap/web/images/` with name korho-logo.png. Recommended image resolution is 420x150. Image height can varie with your logo style. Image can be bigger or smaller, but it will impact the look of it. You can change the width (and therefore in height as well) of image with CSS changing value of `max-width` defined in CSS (within <style>-tags).
    
# 4. Last words
This is my first GitHub post, please tell me if i can somehow improve this! :) If you need help setting this up, please post issue with your index.html attached.

*Best regards,*

*korho*
