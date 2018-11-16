# yolov3-caffe

1. caffe add upsample
  caffe-root
  
  add include/caffe/layers/upsample_layer.hpp
  add src/caffe/layers/upsample_layer.cpp
  add src/caffe/layers/upsample_layer.cu
  change src/caffe/proto/caffe.proto    (row 325, 423, 1438~1441)
  add src/caffe/test/test_upsample_layer.cpp
