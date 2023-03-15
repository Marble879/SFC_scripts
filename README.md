# SFC_scripts

# Docker guide

Here are the steps we took to build and run the image, and then modify ipynbs:
1. build the image via the dockerfile inside the SFC_scripts repo: ```docker build -t python39-jupyter .```
2. start a container via: ```docker run -p 8888:8888 -v $(pwd):/notebooks python39-jupyter```
3. After this, a jupyter notebook session should be started. Directories can now be navigated via the notebook and .ipynbs can be modified.

NOTE: Any modifications done via the docker jupyter session should affect the local files as well
