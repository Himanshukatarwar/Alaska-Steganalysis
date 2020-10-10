# Alaska-Steganalysis
<b>What is steganography?</b> <br><i>Steganography is the practice of concealing a file, message, image, or video within another file, message, image, or video.</i><br><HR>
<p>To understand steganography we need to understand the way that digital images work.Digital image consist of pixels.Pixels are the sample of original Images.More pixels more accurate the image.Every pixels store in 8bits format .For example :Let consider RGB image  has RGB(218,150,149) value and store in 8 bits format like :R=11011010 ,G=10010110,B=10010101.Rightmost bit is the most significant bit and the leftmost bit is the least significant bit .Least significant bit open gate for the steganography .Most significant bit are taken from the image and least significant bit are change with the encrypted data.</p>
  <p>In this problem,Steganography are not on pixels of images.</p>
<b>Data</b> :<p> Dataset contains a large number of unaltered images, called the "Cover" image, as well as corresponding examples in which information has been hidden using one of three steganography algorithms (JMiPOD, JUNIWARD, UERD). The goal of the competition is to determine which of the images in the test set (Test/) have hidden messages embedded.


<b >Note</b>:
<ul>
<li>Each embedding algorithm is used with the same probability.
<li>The payload (message length) is adjusted such that the "difficulty" is approximately the same regardless the content of the image. Images with smooth content are used to hide shorter messages while highly textured images will be used to hide more secret bits. The payload is adjusted in the same manner for testing and training sets.
<li>The average message length is 0.4 bit per non-zero AC DCT coefficient.
<li>The images are all compressed with one of the three following JPEG quality factors: 95, 90 or 75.
</ul>

<b >Files</b>:
<ul>
    <li>Cover/ contains 75k unaltered images meant for use in training.
<li>JMiPOD/ contains 75k examples of the JMiPOD algorithm applied to the cover images.
<li>JUNIWARD/contains 75k examples of the JUNIWARD algorithm applied to the cover images.
<li>UERD/ contains 75k examples of the UERD algorithm applied to the cover images.
<li>Test/ contains 5k test set images. These are the images for which you are predicting.

<h2> Metric:</h2><br>
<h3>Weighted AUC</h3><br>
    <p>In order to focus on reliable detection with an emphasis on low false-alarm rate, metric are used here is weighted AUC. To calculate the weighted AUC, each region of the ROC curve is weighted according to these chosen parameters:
<br>
tpr_thresholds = [0.0, 0.4, 1.0]<br>
weights = [2, 1]
<br>
In other words, the area between the true positive rate of 0 and 0.4 is weighted 2X, the area between 0.4 and 1 is now weighed (1X). The total area is normalized by the sum of weights such that the final weighted AUC is between 0 and 1.
