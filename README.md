# ChatGPT Example scripts 23-Feb-23

### Install chrome

Here is what I asked ChatGPT:

<img width="746" alt="image" src="https://user-images.githubusercontent.com/6307051/221001466-f197b384-e00b-439a-8662-55fd7c1b1841.png">

Here is the code it produced, which I mostly used with some modifications:

```bash
#!/bin/bash

# Check if Adobe Acrobat Reader is already installed
if [ -d "/Applications/Adobe Acrobat Reader DC.app" ]; then
  echo "Adobe Acrobat Reader is already installed"
  exit 0
fi

# Download the latest version of Adobe Acrobat Reader package from Adobe's website
curl -o "AcroRdrDC_${version}_MUI.pkg" "https://ardownload2.adobe.com/pub/adobe/reader/mac/AcrobatDC/${version}/AcroRdrDC_${version}_MUI.pkg"

# Install Adobe Acrobat Reader package
sudo installer -pkg "AcroRdrDC_${version}_MUI.pkg" -target /

# Clean up the downloaded package file
rm "AcroRdrDC_${version}_MUI.pkg"

echo "Adobe Acrobat Reader has been installed successfully"
```


### Install Zoom

here is what I asked ChatGPT:

<img width="776" alt="image" src="https://user-images.githubusercontent.com/6307051/221002348-727bed0c-ecaf-4bf4-b7d6-2f7787188372.png">

```bash
#!/bin/bash

# Check if Zoom is already installed
if [[ $(command -v zoom) ]]; then
  # Zoom is already installed, check for updates
  echo "Zoom is already installed. Checking for updates..."
  /usr/local/bin/zoomusupdate --install
else
  # Zoom is not installed, install it
  echo "Zoom is not installed. Installing..."
  cd ~/Downloads
  curl -LO "https://zoom.us/client/latest/Zoom.pkg"
  sudo installer -pkg Zoom.pkg -target /
  rm Zoom.pkg
fi

```
