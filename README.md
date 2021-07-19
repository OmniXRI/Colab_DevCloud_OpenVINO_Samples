# Colab_DevCloud_OpenVINO_Samples
這裡分享一些可以從Google Colab或者Intel DevCloud上執行的OpenVINO Jypyter Notebook Python範例。只需將對應範例下載到自己的電腦上，再上傳到自己的Google Driver或DevCloud雲端儲存空間即可執行。  
主要參考範例是從Intel OpenVINO官方文件中整理而得，更多內容可參考Open Model Zoo Demos https://docs.openvinotoolkit.org/latest/omz_demos.html  

Colab及DevCloud版本最大差異為前者每次都需重新安裝一次OpenVINO，且執行時通常要執行/opt/intel/openvino/bin/setupvars.sh來設定環境變數，而後者已自帶OpenVINO且已將環境變數設定好，不需再次執行。  

每個範例程式都能獨立執行，工作流程大致相同，下載模型、轉換模型成IR、準備測試影像及進行推論，但其中細節會略有不同，請仔細比較其中差異。  

**Colab_OpenVINO_Face_Detection.ipynb**  
**DevCloud_OpenVINO_Face_Detection.ipynb**   
Intel's Pre-trained Model人臉偵測範例，主要使用模型face-detection-retail-0005，搭配/inference_engine/demos/object_detection_demo/python/object_detection_demo.py執行推論工作。  
![](https://raw.githubusercontent.com/OmniXRI/Colab_DevCloud_OpenVINO_Samples/main/images/face_detection_output.png)

**Colab_OpenVINO_Pose_Estimation.ipynb**   
**DevCloud_OpenVINO_Pose_Estimation.ipynb**   
Intel's Pre-trained Model人體姿態估測範例，主要使用模型human-pose-estimation-0007，搭配/inference_engine/demos/human_pose_estimation_demo/python/human_pose_estimation_demo.py執行推論工作。  
![](https://raw.githubusercontent.com/OmniXRI/Colab_DevCloud_OpenVINO_Samples/main/images/pose_estimation_output.png)

**Colab_OpenVINO_Image_Classification.ipynb**   
**DevCloud_OpenVINO_Image_Classification.ipynb**   
Public Pre-trained Model影像分類範例，主要使用模型resnet-34-pytorch，搭配/inference_engine/samples/python/hello_classification/hello_classification.py執行推論工作。  
![](https://raw.githubusercontent.com/OmniXRI/Colab_DevCloud_OpenVINO_Samples/main/images/Image_classification_input.png)

**Colab_OpenVINO_Open_Closed_Eye_ONNX.ipynb**
本範例和上一個影像分類相同，主要使用open-closed-eye-0001，搭配/inference_engine/samples/python/hello_classification/hello_classification.py執行推論工作。  
該模型為ONNX格式，所以需先轉換成IR格式(bin, xml)。另外該模型輸出只有兩個分類，classid=0為閉眼，classid=1為張眼，不須再引入標籤標檔(Label)。  
![](https://raw.githubusercontent.com/OmniXRI/Colab_DevCloud_OpenVINO_Samples/main/images/open_closed_eye_output.png)

**Colab_OpenVINO_Face_Head_Gaze.ipynb**  
**DevCloud_OpenVINO_Face_Head_Gaze.ipynb**  
OpenVINO人臉定位、特徵提取、頭部姿態估測及注視點偵測範例程式，主要使用下列四項模型。
*    人臉定位　 face-detection-retail-0004  
*    人臉特徵點 landmarks-regression-retail-0009  
*    頭部姿態　 head-pose-estimation-adas-0001  
*    注視點估測 gaze-estimation-adas-0002  

由於Intel OpenVINO官方未提供Head Pose, Gaze Estimation Python範例程式，這裡參考 https://github.com/LCTyrell/Gaze_estimation 進行測試。原程式使用OpenVINO 2020.3.194 (2020.3 LTS)版本，經測試不適用於 2021.3.394版本。  
![](https://raw.githubusercontent.com/OmniXRI/Colab_DevCloud_OpenVINO_Samples/main/images/Face_Head_Gaze_output.PNG)

**Colab_OpenVINO_Sound_Classification.ipynb**   
**DevCloud_OpenVINO_Sound_Classification.ipynb**   
Public Pre-trained Model聲音分類範例，主要使用模型Aet及ESC-50環境音資料集，搭配/inference_engine/demos/sound_classification_demo/python/sound_classification_demo.py執行推論工作。  
![](https://github.com/OmniXRI/Colab_DevCloud_OpenVINO_Samples/blob/main/images/esc50.gif)

**Colab_OpenVINO_Sound_Segmentation.ipynb**   
**DevCloud_OpenVINO_Sound_Segmentation.ipynb**   
Public Pre-trained Model影像分割範例，主要使用模型deeplabv3，搭配/inference_engine/demos/segmentation_demo/python/segmentation_demo.py執行推論工作。    
![](https://github.com/OmniXRI/Colab_DevCloud_OpenVINO_Samples/blob/main/images/image_segmentation_output.png)
