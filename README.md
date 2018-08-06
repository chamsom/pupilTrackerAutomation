# pupilTrackerAutomation

## Abstract: 

The rate at which a pupil dilates is a biomarker for Parkinson’s disease. Ophthalmologists can analyze the pupil dilation rate by shining a light at the eye and observing how the pupil reacts when the light is taken away. A five-minute video of the procedure takes a medical student a few days to go through, analyzing each frame of the video. Instead of this, we wanted to create a program to help automate the process. The optometrist can analyze the data and properly diagnose with the patient with early onset Parkinson’s, leading to preventative treatment for the patient. The program automatically selects the pupil and tracks the center. Then, it returns the rate of change of the pupil over time. The user can confirm the selection is correct, or fix the selection when needed. We are be able to adjust for any movement in the video. The result is a graph that shows the size of the pupil over time, as well as data with the size at each point. This allows them to make the process go from a few days to a few hours. This will help the medical students focus on getting real world experience instead of having to spend their time on tracking the pupil size.

## Dependencies: 

Utilizing scipy.optimize package: Nelder-Mead Simplex & SLSQP Algorithm. Matplotlib, NumPy, Pillow, PyLab, & OpenCV2.

## Hugh Circle Transform (utilizing ellipse transform method):

Still needs fixing to analyze a custom image. We are unsure as to why the method is returning an image that cannot be analyzed.  Possible that io.imRead does not perform the same function as the data.directoryFile() used in example code.

## Canny Edge Detection:

**cv.Canny():** First argument is input image. Second & Third argument represent minVal & maxVal respectively. Note that the third argument is aperture_size and it is utilized for finding image gradients. (Third argument defaults to a value of 3. We may implement edge detection before HCT is utilized on a pupil frame so that we can remove persistent false circle detection).

## Description of the parameters for the cv2.HoughCircles function (Note that these parameters will have to be manually adjusted per frame in order to achieve optimal pupil fit)

**img** Input image (grayscale)

**cv2.HOUGH_GRADIENT** Define the detection method

**dp** = 2 The inverse ratio of resolution

**min_dist** = 50 Minimum distance between detected centers

**param1** = 30 Upper threshold for the internal Canny edge detector

**param2** = 195 Threshold for center detection.

**minRadius** = 100 Minimum radio to be detected. If unknown, put zero as default

**maxRadius** = 200 Maximum radius to be detected. If unknown, put zero as default
