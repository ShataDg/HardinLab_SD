### Steps to follow to run the Fiji-Cellpose-Trackmate pipeline to analyse 4D Nomarski Microscopy images of C.elegans embryo for tracking epidermal cell development

#### The following steps were executed on a subset comprising 31 timepoints with 26 slices in each timepoint

1. Open Fiji (making sure that the latest updates have been applied)
2. Drag and drop the FindFocusMacroEdge.ijm in Fiji
3. Fiji will ask to be pointed to the (a) folder containing images and (b) folder where the output should be saved
4. Fiji will also ask for details (number of z planes and time-lapse planes) related to the image stacks, and show the progress of hyperstack creation in a separate window

![alt text](<Screenshot 2024-02-26 at 11.09.51 AM.png>)

![alt text](<Screenshot 2024-02-26 at 11.36.38 AM.png>)

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
   
   ![image](https://github.com/ShataDg/HardinLab_SD/assets/139376717/86f8468a-6083-46fc-a587-413f98bc8c5a)

7. Click 'Update' again and then on 'Manage Update Sites'. Check the 'Trackmate-Cellpose' box and restart Fiji.

![Screenshot 2024-02-16 at 1 32 18 PM](https://github.com/ShataDg/HardinLab_SD/assets/139376717/aa239d3a-ec99-40af-b151-fc564fda548b)

8. Drag and drop the image created in steps 3 and 4
9. Click on 'Plugins' --> 'Tracking' --> 'TrackMate'

![Screenshot 2024-02-16 at 1 36 27 PM](https://github.com/ShataDg/HardinLab_SD/assets/139376717/a932038c-8a75-485c-ac83-ff4328d63994)

10. In the TrackMate window, click on 'Next'

![image](https://github.com/ShataDg/HardinLab_SD/assets/139376717/95799681-dbef-423c-8eda-a7a56df20bb2)

11. Set the detector to 'Cellpose detector' and click on 'Next'

![Screenshot 2024-02-16 at 1 40 15 PM](https://github.com/ShataDg/HardinLab_SD/assets/139376717/2c4000f9-8c8c-49cb-a9ba-99bd0fff4e7f)

12. Set the path to Cellpose and the cutsom model and click on Next

![image](https://github.com/ShataDg/HardinLab_SD/assets/139376717/572d75e9-16ae-4b9d-8b88-c2f56df686e6)

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












