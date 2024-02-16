#### Steps to follow to run the Fiji-Cellpose-Trackmate pipeline to analyse 4D Nomarski Microscopy images of C.elegans embryo for tracking epidermal cell development

1. Open Fiji (making sure that the latest updates have been applied)
2. Drag and drop the FindFocusMacroEdge.ijm in Fiji
3. Fiji will ask to be pointed to the (a) folder containing images and (b) folder where the output should be saved
4. Fiji will also ask for details related the image stacks
   
   ![image](https://github.com/ShataDg/HardinLab_SD/assets/139376717/3baca39e-d749-44c8-ba8b-a872ae87447f)

5. Ensure that cellpose has been installed and is running on your system
   Code to help installation issue with Cellpose GUI on Mac M2 (running TrackMate-Cellpose does not necessarily require this step, it only requires a working version of cellpose on the system)

   a. Create a virtual environment using Python 3.9 with libraries pyqt, pyqtgraph, and imagecodecs
   <br> ```conda create --name cellpose -y python=3.9 pyqt imagecodecs pyqtgraph```

   b. Activate the virtual environment
   <br> ```conda activate cellpose```

   c. Install cellpose and required dependencies
   <br> ```pip install cellpose pyqt6 superqt```

   d. Start Cellpose GUI
   <br> ```cellpose```

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

12. Set the path to cellpose and the cutsom model

![image](https://github.com/ShataDg/HardinLab_SD/assets/139376717/e915e564-38c7-425b-8bd2-b4db66984911)

13. 












