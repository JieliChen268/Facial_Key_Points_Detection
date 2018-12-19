# Facial_Key_Points_Detection
## Summary
Detecting facial key points is a very challenging problem since facial features vary greatly due to 3D pose, size, position and illumination conditions. This project describes an effort to predicting facial key points positions on greyscale images from the Facial Detection (2016) Kaggle competition dataset. The methodology of this project involves five steps with cycle for continuous improvement: 1). Data understanding; 2). Data preparation; 3). Modeling; 4). Evaluations; 5). Prediction on new data set.  The training dataset we used are from Kaggle competition including 7049 images of 96 x 96 pixel with 15 facial key points x, y positions on it. The evaluation is based on root mean absolute error (RMSE) on the training dataset. The improvement goal is to reduce RMSE to as small as possible data augmentation and deep learning model tuning. Lastly, I used tuned model, prediction results to fill null value in the train dataset, mirror images, histogram stretching and contrast jittering to reduce RMSE value from 3.21 to 2.17.  

## objective
The objective of this project is to predict keypoint positions on face images. This can be used as a building block in several applications, such as:

- tracking faces in images and video
- analysing facial expressions
- detecting dysmorphic facial signs for medical diagnosis
- biometrics / face recognition
- Detecing facial keypoints is a very challenging problem.  F
acial features vary greatly from one individual to another, and even for a single individual, there is a large amount of variation due to 3D pose, size, position, viewing angle, and illumination conditions. 
Computer vision research has come a long way in addressing these difficulties, but there remain many opportunities for improvement.

# Data Description
Each predicted keypoint is specified by an (x,y) real-valued pair in the space of pixel indices. There are 15 keypoints, which represent the following elements of the face:

left_eye_center, right_eye_center, left_eye_inner_corner, left_eye_outer_corner, right_eye_inner_corner, right_eye_outer_corner, left_eyebrow_inner_end, left_eyebrow_outer_end, right_eyebrow_inner_end, right_eyebrow_outer_end, nose_tip, mouth_left_corner, mouth_right_corner, mouth_center_top_lip, mouth_center_bottom_lip

Left and right here refers to the point of view of the subject.

In some examples, some of the target keypoint positions are misssing (encoded as missing entries in the csv, i.e., with nothing between two commas).

The input image is given in the last field of the data files, and consists of a list of pixels (ordered by row), as integers in (0,255). The images are 96x96 pixels.

Data files

training.csv: list of training 7049 images. Each row contains the (x,y) coordinates for 15 keypoints, and image data as row-ordered list of pixels.
test.csv: list of 1783 test images. Each row contains ImageId and image data as row-ordered list of pixels
submissionFileFormat.csv: list of 27124 keypoints to predict. Each row contains a RowId, ImageId, FeatureName, Location. FeatureName are "left_eye_center_x," "right_eyebrow_outer_end_y," etc. Location is what you need to predict. 

## Evaluation
Submissions are scored on the root mean squared error. RMSE is very common and is a suitable general-purpose error metric. Compared to the Mean Absolute Error, RMSE punishes large errors:

where y hat is the predicted value and y is the original value.
