# TDVR
A graph-based approach to transformation driven visual learning

*Data2Graph2Sents* -> The attribute value data is converted into graphs. Initial Graph, Final Graph, and Transformation Graph
  Architecture: 
    Data -> Graph (Init Graph, Final Graph, Transformation Stmts)
    Init Encoding = Weisfeiler Machine (Init Graph)
    Final Encoding = Weisfeiler Machine (Final Group)

*GraphDiffToTransformation* -> The Init Encoding and Final Encoding will be used as an input to the Encoder and the Decoder output will be the output
Architecture:
  Data -> Init Encoding -> Encoder-1 -> encoder_1
       -> Final Encoding -> Encoder-2 -> encoder_2
       -> (encoder_1-encoder_2) -> Decoder -> output
         
*SimpleLinear* -> The Init, Final and Output Representations are converted into one hot encoded vectors. The one hot encoded vectors are used as input for the Network
Architecture:
  Data -> Init_vec = OneHotEncoder(Init)
       -> Final_vec = OneHotEncoder(Final)
       -> Init_vec - Final_vec
       -> Output' = SimpleLinear(Init_vec, Final_vec)
