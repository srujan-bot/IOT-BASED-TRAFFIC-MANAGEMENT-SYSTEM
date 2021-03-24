1) Setting up Raspberry PI 4 software modules

Connect to Raspberry PI 4 using SSH connection. Open a terminal window and type following 
commands.
sudo apt-get update
sudo apt-get upgrade

2) TensorFlow installation
cd ~
sudo apt-get update
sudo apt-get dist-upgrade
pip3 install tensorflow
sudo apt-get install libatlas-base-dev
sudo pip3 install pillow lxml jupyter matplotlib cython
sudo apt-get install python-tk
sudo apt-get install libjpeg-dev libtiff5-dev libjasper-dev libpng12-dev
sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
sudo apt-get install libxvidcore-dev libx264-dev
sudo apt-get install qt4-dev-tools libatlas-base-dev
sudo pip3 install opencv-python
sudo apt-get install protobuf-compiler
mkdir tensorflow1
cd tensorflow1
git clone https://github.com/tensorflow/models.git --depth 1
# sudo vi ~/.bashrc and at the end add following two lines
# Set PYTHONPATH for TensorFlow
# export 
PYTHONPATH=$PYTHONPATH:/home/pi/tensorflow1/models/research:/home/pi/tensorflo
w1/models/research/slim
cd /home/pi/tensorflow1/models/research
protoc object_detection/protos/*.proto --python_out

3) Opencv installation
cd ~/opencv/
rm -rf opencv
rm -rf opencv_contrib
rm -rf installation
sudo apt-get update
sudo apt-get upgrade
sudo apt-get clean
sudo apt-get autoremove
sudo apt-get install build-essential cmake git unzip pkg-config
sudo apt-get install libjpeg-dev libpng-dev libtiff-dev
sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev
sudo apt-get install libgtk2.0-dev libcanberra-gtk*
sudo apt-get install libxvidcore-dev libx264-dev libgtk-3-dev
sudo apt-get install python3-dev python3-numpy python3-pip
sudo apt-get install python-dev python-numpy
sudo apt-get install libtbb2 libtbb-dev libdc1394-22-dev
sudo apt-get install libv4l-dev v4l-utils
sudo apt-get install libjasper-dev libopenblas-dev libatlas-base-dev libblas-dev
sudo apt-get install liblapack-dev gfortran
sudo apt-get install gcc-arm*
sudo apt-get install protobuf-compiler
sudo apt-get install libhdf5-dev libhdf5-serial-dev libhdf5-103
sudo apt-get install libqtgui4 libqtwebkit4 libqt4-test python3-pyqt5
sudo apt-get build-dep libqt5gui5
sudo apt install qtbase5-dev
sudo apt-get -y install libgtk2.0-dev pkg-config
38 | P a g e
cd ~
unzip opencv.zip
unzip opencv_contrib.zip
mv opencv-4.2.0 opencv
mv opencv_contrib-4.2.0 opencv_contrib
python3 --version
which python 3.7
echo "export VIRTUALENV/mkWRAPPER_PYTHON=/usr/bin/python3.7" >> ~/.bashrc
source ~/.bashrc
sudo pip3 install virtualenv
sudo pip3 install virtualenvwrapper
echo "export WORKON_HOME=$HOME/.virtualenvs" >> ~/.bashrc
echo "source /usr/local/bin/virtualenvwrapper.sh" >> ~/.bashrc
source ~/.bashrc
mkvirtualenv cv420
pip3 install numpy
cd ~/opencv
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=RELEASE \
 -DCMAKE_INSTALL_PREFIX=/usr/local \
 -DOPENCV_EXTRA_MODULES_PATH=~/opencv_contrib/modules \
 -DINSTALL_C_EXAMPLES=ON \
 -DINSTALL_PYTHON_EXAMPLES=ON \
 -DFORCE_VTK=ON \
 -DWITH_TBB=ON \
 -D BUILD_TBB=ON \
 -D BUILD_TESTS=OFF \
 -D WITH_EIGEN=OFF \
 -DWITH_V4L=ON \
 -D WITH_LIBV4L=ON \
 -DWITH_QT=ON \
 -DWITH_CUBLAS=ON \
 -DCUDA_NVCC_FLAGS="-D_FORCE_INLINES" \
 -DWITH_GDAL=ON \
 -DWITH_XINE=ON \
 -DWITH_OPENGL=ON \
 -DENABLE_NEON=ON \
 -DENABLE_VFPV3=ON \
 -DWITH_OPENMP=ON \
 -DBUILD_TIFF=ON \
 -DWITH_FFMPEG=ON \
 -DWITH_GSTREAMER=ON \
 -DBUILD_TESTS=OFF \
 -DINSTALL_C_EXAMPLES=OFF \
 -DINSTALL_PYTHON_EXAMPLES=OFF \
 -DBUILD_NEW_PYTHON_SUPPORT=ON \
 -DBUILD_opencv_python3=TRUE \
 -DOPENCV_ENABLE_NONFREE=ON \
 -DOPENCV_EXTRA_EXE_LINKER_FLAGS=-latomic \
 -DCMAKE_SHARED_LINKER_FLAGS=-latomic \
 -DOPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules \
 -DOPENCV_GENERATE_PKGCONFIG=ON \
 -DBUILD_EXAMPLES=ON ..
sudo make -j$(nproc)
sudo make install

4) Tesseract installation
cd ~
sudo apt-get update
sudo apt-get upgrade
sudo apt install libatlas3-base libsz2 libharfbuzz0b libtiff5 libjasper1 libilmbase12 libopenexr22 
libgstreamer1.0-0 libavcodec57 libavformat57 libavutil55 libswscale4 libqtgui4 libqt4-test 
libqtcore4
sudo apt install libgtk2.0/dev pkg-config
sudo pip3 install opencv-contrib-python libwebp6
sudo apt install tesseract-ocr
sudo apt install libtesseract-dev
sudo pip install pytesseract


5) Pytesseact Image to String Conversion Modes
# 
# OEM Modes:
# 0 Legacy engine only.
# 1 Neural nets LSTM engine only.
# 2 Legacy + LSTM engines.
# 3 Default, based on what is available.
#
# Page Segmentation Modes (PSM):
#
# 0 Orientation and script detection (OSD) only.
# 1 Automatic page segmentation with OSD.
# 2 Automatic page segmentation, but no OSD, or OCR.
# 3 Fully automatic page segmentation, but no OSD. (Default)
# 4 Assume a single column of text of variable sizes.
# 5 Assume a single uniform block of vertically aligned text.
# 6 Assume a single uniform block of text.
# 7 Treat the image as a single text line.
# 8 Treat the image as a single word.
# 9 Treat the image as a single word in a circle.
# 10 Treat the image as a single character.
# 11 Sparse text. Find as much text as possible in no particular order.
# 12 Sparse text with OSD.
# 13 Raw line. Treat the image as a single text line, bypassing hacks that are Tesseract-specific.
#

