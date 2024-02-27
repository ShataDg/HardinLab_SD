## Steps to follow to run the Fiji-Cellpose-Trackmate pipeline to analyse 4D Nomarski Microscopy images of C.elegans embryo for tracking epidermal cell development

## The following steps were executed on a subset comprising 31 timepoints with 26 slices in each timepoint

### Steps 1 - 4: Creating a hyperstack from the individual time-points and slices
1. Open Fiji (making sure that the latest updates have been applied)  
2. Drag and drop the FindFocusMacroEdge.ijm in Fiji  
3. Fiji will ask to be pointed to the (a) folder containing images and (b) folder where the output should be saved  
4. Fiji will also ask for details (number of z planes and time-lapse planes) related to the image stacks, and show the progress of hyperstack creation in a separate window

![image](https://github.com/ShataDg/HardinLab_SD/blob/c0e95afcdb46927093f3d8c7d6b557cb2608279f/Images/Screenshot%202024-02-26%20at%2011.09.51%E2%80%AFAM.png)



### Steps 5 - ..: Running Cellpose-detector within Trackmate

5. To use the Cellpose detector within Trackmate, ensure that cellpose has been installed and is running on your system
   
   '''  
   The following code should help address installation issues with the Cellpose GUI on Mac M2 (running TrackMate-Cellpose does not necessarily require this step, it only requires a working version of cellpose on the system)

   a. Create a virtual environment using Python 3.9 with libraries pyqt, pyqtgraph, and imagecodecs
   <br> ```conda create --name cellpose -y python=3.9 pyqt imagecodecs pyqtgraph```

   b. Activate the virtual environment
   <br> ```conda activate cellpose```

   c. Install cellpose and required dependencies
   <br> ```pip install cellpose pyqt6 superqt```

   d. Start Cellpose GUI
   <br> ```cellpose```

   '''
6. Click on 'Help' in Fiji, and then 'Update' and restart Fiji to apply the updates
   
![image](https://github.com/ShataDg/HardinLab_SD/blob/c45605374e34e0aba31d19ea35a333863fe31d8d/Images/Screenshot%202024-02-26%20at%207.05.41%E2%80%AFPM.png)

7. Click 'Update' again and then on 'Manage Update Sites'. Check the 'Trackmate-Cellpose' box and restart Fiji.

![image](https://github.com/ShataDg/HardinLab_SD/blob/99b7570a915911baaf8524c5130757f4586e26d2/Images/Screenshot%202024-02-26%20at%207.09.38%E2%80%AFPM.png)

8. Drag and drop in Fiji the hyperstack created in steps 1 - 4

![image](<Images/Screenshot 2024-02-26 at 11.45.14 AM.png>)

9.  Click on 'Plugins' --> 'Tracking' --> 'TrackMate'

![image](<Images/Screenshot 2024-02-26 at 7.16.24 PM.png>)

10.  In the TrackMate window, click on 'Next'

![image](<Images/Screenshot 2024-02-26 at 1.08.39 PM.png>)

**N.B. At this step, you would only need to check that the number of timepoints is being correctly identified and appearing under 'T'. Since the image that was dragged and dropped was a hyperstack, you would not need to enter a value under 'Z'.**

11. Set the detector to 'Cellpose detector' and click on 'Next'

![image](<Images/Screenshot 2024-02-26 at 7.41.31 PM.png>)

12. Set the paths to Cellpose (i.e. where Cellpose was installed) and the cutsom model (i.e. Cellpose models trained on the images - for this example we are using the 'hardin' model, trained to identify ~6 migrating cells of interest)) and click on Next

![image](<Images/Screenshot 2024-02-26 at 7.54.15 PM.png>)

13. Once Cellpose has finished running, it will output the number of spots detected; click on 'Next'

![image](https://github.com/ShataDg/HardinLab_SD/assets/139376717/bcefae44-a265-487b-add5-5394f6f96cac)

14. Perform 'Intial Thresholding' based on your biological question and click 'Next'

![Screenshot 2024-02-16 at 2 20 49 PM](https://github.com/ShataDg/HardinLab_SD/assets/139376717/e94af9f4-d50c-4fff-95c6-ef6d7b3c2d04)

15. Choose the tracker





======================================================================================

### Running the pipeline on the set of images received Feb, 2024

1. The macro produced a hyperstack but gave this error message

![image](https://github.com/ShataDg/HardinLab_SD/assets/139376717/753f3502-85fa-4098-b81f-5c8e5a9998ed)

2. Trackmate with Cellpose detector was used to analyse the hyperstack

![image](https://github.com/ShataDg/HardinLab_SD/assets/139376717/82f6ab27-fa6d-415b-8ecf-94a8720bad86)












