## Steps to follow to run the Fiji-Cellpose-Trackmate pipeline to analyse 4D Nomarski Microscopy images of C.elegans embryo for tracking epidermal cell development

## The following steps were executed on a subset comprising 31 timepoints with 26 slices in each timepoint

### Steps 1 - 4: Creating a hyperstack from the individual time-points and slices
1. Open Fiji (making sure that the latest updates have been applied)  
2. Drag and drop the FindFocusMacroEdge.ijm in Fiji  
3. Fiji will ask to be pointed to the (a) folder containing images and (b) folder where the output should be saved  
4. Fiji will also ask for details (number of z planes and time-lapse planes) related to the image stacks, and show the progress of hyperstack creation in a separate window

![image](https://github.com/ShataDg/HardinLab_SD/blob/c0e95afcdb46927093f3d8c7d6b557cb2608279f/Images/Screenshot%202024-02-26%20at%2011.09.51%E2%80%AFAM.png)


### Steps 5 - 13: Running Cellpose-detector within Trackmate

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

12. Set the paths to Cellpose (i.e. where Cellpose was installed) and the cutsom model (i.e. Cellpose models trained on the images - for this example we are using the 'hardin' model, trained to identify ~6 migrating cells of interest) and click on Next

![image](<Images/Screenshot 2024-02-26 at 7.54.15 PM.png>)

13. Once Cellpose has finished running, it will output the number of spots detected; click on 'Next'

![image](<Images/Screenshot 2024-02-26 at 8.11.42 PM.png>)

### Steps 14 - : Running tracker and plotting

14.  Perform 'Intial Thresholding' based on your biological question and click 'Next' (for this example, no thresholding was performed)

![image](<Images/Screenshot 2024-02-26 at 8.24.08 PM.png>)

15. Set filters on spots (for this example, based on qaulity 488 out of 490 spots were inlcuded for analysing in the subsequent steps) and click 'Next'

![image](<Images/Screenshot 2024-02-26 at 8.32.15 PM.png>)

16. Select the tracker (Simple LAP tracker was used in the original pipeline and was used for this examplle as well); click on 'Next'

![image](<Images/Screenshot 2024-02-26 at 8.38.37 PM.png>)

17. Set the parameters for the Simple LAP tracker (for this example, the default parameters were used); click on 'Next'

![image](<Images/Screenshot 2024-02-26 at 8.41.14 PM.png>)

18. TrackMate will inform the number of detected tracks; click on 'Next'

![image](<Images/Screenshot 2024-02-26 at 8.46.05 PM.png>)

19. Set filters on tracks by selecting the appropriate filtering parameter from the dropdown (for this example, the filter was set based on track duration, including tracks with a duration of < 427.64ms - 22 of the 23 detected tracks were included)

![image](<Images/Screenshot 2024-02-26 at 8.53.40 PM.png>)

20. Click on the wrench icon at the bottom of the window to set the display parameters (for this example, spots and trcaks were colored by 'Track means Y' and the color scale was set based on the highest and lowest values)

![image](<Images/Screenshot 2024-02-26 at 9.11.32 PM.png>)

![image](<Images/Screenshot 2024-02-26 at 9.11.32 PM.png>)

21. 













