#darknet yolov3 trained model (yolov3.cfg, yolov3.weights) convert to caffe model (yolov3.prototxt, yolov3.caffemodel)

1. add upsample layer in caffe  
  
    in caffe-root  
    
    add include/caffe/layers/upsample_layer.hpp  
    add src/caffe/layers/upsample_layer.cpp  
    add src/caffe/layers/upsample_layer.cu  
    change src/caffe/proto/caffe.proto    (row 325, 423, 1438~1441)  
    add src/caffe/test/test_upsample_layer.cpp  

2. compiler  caffe  

    cd <caffe_root>  
    source activate pycaffe  
    
    make clean  
    make all -j32  
    make runtest
    cd .build_release/test  
    ./test_upsample_layer.testbin  
    make pycaffe  
    
3. darknet convert to caffe  
  
    git clone https://github.com/marvis/pytorch-caffe-darknet-convert.git  
    unzip pytorch-caffe-darknet-convert.zip  
    cd  pytorch-caffe-darknet-convert  
    
    it should used in env pytorch and only support yolov1, yolov2 convert to caffe, so it is necessary for me to make it support yolov3.  
    change the file  darknet2caffe.py
    
    source activate pytorch
    python darknet2caffe-yolov3.py yolov3.cfg yolov3.weights yolov3.prototxt yolov3.caffemodel
