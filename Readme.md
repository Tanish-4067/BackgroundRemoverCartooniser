
MODEL ARCHITECTURE = semantic segmentation using U-Net (background removal)

		            cartooning using GANs and VGG19


Dataset Creating   (Model was trained using Kaggle)
We used the COCO dataset for extracting out all the photos with people. 
There were around 65000 photos which we used to train our model to create masks.

For cartooning, we used 10000 photos of real-world faces from the FFHQ dataset and around 4000 photos of real-world landscapes from Kaggle. 
For cartoon photos, we used 8000 stills from 2 anime shows in regular intervals and created the cartoon-scenery dataset with that. and extracted 10000 cartoon-faces randomly from a Kaggle anime faces dataset containing around 200k images.


Training   (Model was trained using Kaggle)
For background removal, we used the UNET architecture and trained it using COCO dataset Human images.

For cartooning, we referred  https://systemerrorwang.github.io/White-box-Cartoonization/paper/06791.pdf
It involved generating the output image with the help of Generator and then output was discriminated with cartoon images
on the basis of texture and surface representation. And then, Structural representation of output, Output and Input were fed
to pretrained VGG19 model. Thus, we minimised 4 losses - 2 from 2 discriminators and 2 from VGG19.


Testing the model   (Model was tested using Google COLAB)
After training all the weights and models were saved.
-> model can used from TestingModels.ipynb(present in root folder)
-> The input images should be put in /Input folder
-> then the Learned models should be downloaded and extracted in the root folder(link to the models is present in  TestingModels.ipynb)
-> after running the model, Output images will be present in /Output 



Our model shows great potential but due to limited time and computational power, we trained our model for only 7.5 hours 
but still, it showed a validation accuracy of about 94%.