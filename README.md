# yolov3 to caffe

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
    
