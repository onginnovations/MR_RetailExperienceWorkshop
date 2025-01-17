---
title: Importing MRTK3 into a new Unity project 
---
### [Previous Section: Introduction](1-introduction.md)

# Starting and Configuring a New Unity Project

We'll start by creating a new Unity project and configuring it for Windows Mixed Reality development.  

## Create a New Unity Project

1. Launch the **Unity Hub**.

2. In the **Projects** tab, click **New Project**.

3. Click the drop-down under **New project** and select the appropriate editor version (Unity 2020.3 LTS).

4. Ensure the chosen template is **3D Sample Scene (URP)**. You may need to navigate to the **All Templates** tab to see this option.

    >**Note:**
    Creating your project using 3D Sample Scene (URP) may help increase the performance of your application.

5. In the **Project name** box, enter a name for your project--for example, "MRTKV3_Showroom."

6. In the **Location** box, click the folder icon, and then navigate to the folder where you want to save your project or create a new folder.

7. Click **Create Project**. This opens your project in Unity.

    >**Caution:**
    When working on Windows, there is a file path limit of 255 characters. Unity may fail to compile your app if any file path is longer than 255 characters.

## Import the MRTK3 Unity Package

To import the Mixed Reality Toolkit into your project we'll use the Mixed Reality Feature Tool, which allows developers to discover, update, and import mixed reality feature packages.

1. Download the latest version of the Mixed Reality Feature Tool from the [**Microsoft Download Center**](https://aka.ms/MRFeatureTool).

2. Unzip the folder and double-click **MixedRealityFeatureTool.exe** to launch the Mixed Reality Feature Tool.

    ![A screenshot of launching the Mixed Reality Feature Tool.](img/open-mixed-reality-feature-tool.png)

3. In the Mixed Reality Feature Tool, select **Start**.

    ![A screenshot of selecting start.](img/mixed-reality-feature-tool.png)

4. To access the **MRTK3 preview packages**, click on the **Settings Icon** at the bottom-left of the window. Switch to the **Feature** tab and ensure that the **Show preview releases** button is checked.

    ![A screenshot of accessing MRTK3 preview packages.](img/enable-preview-packages.png)

5. Click on **Ok** to apply the settings.

6. Select the browse button (button highlighted with a red box in the image below), then navigate to your project and open it.

    ![A screenshot of selecting the Browse button.](img/select-browse-button.png)

    >**Note:**
    The Project Path box in the Tool must contain some value, so it inserts a backslash ("_") by default.

7. After you select a folder, the tool checks to ensure that you have selected a folder that contains a valid Unity project. 

8. Select **Discover Features**.

    ![A screenshot of selecting Discover Features](img/project-path.png)

    >**Note:**
    You may need to wait a few seconds while the Tool refreshes the packages from the feeds.

9. On the **Discover Features** page, note that there is a list of seven package groups.

    ![A screenshot of list of seven package groups.](img/NewMicrosoftFeatureTool-Step9.png)

10. Click the **Select All** button next to **MRTK3**. 

    ![A screenshot of selecting all.](img/NewMicrosoftFeatureTool-Step10.png)

    >**Note:**
    The "MRTK Core Definitions package" is the primary package that must be imported and configured to use MRTK with your project. This package includes the core components required to create a mixed reality application.

11. Click the "+" button to the left of **Platform Support** and then select the latest version of the **Mixed Reality OpenXR Plugin**. After you've made your selection(s), click **Get Features**.

    ![A screenshot of selecting the latest version of Mixed Reality OpenXR plugin.](img/NewMicrosoftFeatureTool-Step11.png)


12. Select **Validate** to validate the packages you selected. You should see a dialog that says **No validation issues** were detected. When you do, click **OK**.

13. On the **Import Features** page, in the left-side column, the **Features** displays the packages you just selected. The right-side column shows the **required dependencies**. You can click the **Details** link for any of these items to learn more about them.

14. When you're ready to move on, select **Import**. On the **Review and Approve** page, you can review information about the packages.

15. Select **Approve**.

16. Return to the Unity Editor. You'll see a progress bar showing you that your packages are being imported. You may need to click anywhere in the Unity window to trigger the package import if you do not see the progress bar.

## Configure the Unity Project

1. After Unity has imported the packages, a warning appears asking if you want to enable the backends by restarting the editor. Select **Yes**.

    ![A screenshot of the warning.](img/warning-restart.png)

2. You will encounter another warning asking if you have created a backup. Click on **I Made a Backup, Go Ahead!** Wait for the project to **restart**.

    ![A screenshot of the warning asking if you have backup.](img/backup-created.png)

3. In the menu bar, select **File** > **Build Settings**. If you see an OpenXR Project Validation window or pop-up warning with issues, feel free to ignore the warning as it will be addressed later in this tutorial.

4. In the **Build Settings** window, select **Universal Windows Platform** and click on **Switch Platform**. Follow the instructions below if you do not have the **Universal Windows Platform** module installed in Unity. If you do, feel free to skip to Step 5.

    ![A screenshot of switching platform.](img/switch-platform-mrtk3.png)

    >**Note:**
    To have the Universal Windows Platform option enabled in the Build Settings Window, ensure that Universal windows platform is checked while you download the respective unity version through Unity Hub

    - Click on **settings** of the respective version, then select **Add modules**.

        ![A screenshot of Adding module.](img/add-module.png)

    - Now ensure that **Universal Windows Platform Build Support** is **checked**, then click **Install**.

        ![A screenshot of ensuring Universal Windows Platform Build Support is checked.](img/uwp.png)
    >**Note:**
    To reload the packages and avoid errors, close and re-open the project.

5. Navigate to **Edit** > **Project settings**. Ensure that you're on the **XR Plug-in Management** section with the **Universal Windows Platform** settings (Windows logo tab) displayed.

    ![A screenshot of configuring XR-plug-in Management.](img/xr-plugin-management.png)

6. Select **OpenXR** and wait for the packages to install. There may be a yellow warning triangle next to OpenXR. Hover your cursor over the triangle if you wish to read the message in the popup, and then select the triangle to open the OpenXR Project Validation window.

    ![A screenshot of warning to fix OpenXR.](img/warning-fix-openxr.png)

7. In the **OpenXR Project Validation window**, there may be several issues listed. Select the Fix All button. If you see an issue stating that "at least one interaction profile must be added", feel free to ignore this as this will be covered over the next few steps.

    ![A screenshot of selecting Fix All button.](img/fix-all-openxr.png)

8. Check the **Microsoft HoloLens feature group** checkbox.

    ![A screenshot of enabling the checkbox.](img/microsoft-hololens-feature-group.png)

9. Select the **OpenXR** submenu that is under the XR Plug-in Management menu item, as indicated in the figure. In the **Interaction Profiles** section, select the plus sign (+) button three times, each time choosing one of the following profiles:

    - Eye Gaze Interaction Profile
    - Microsoft Hand Interaction Profile
    - Microsoft Motion Controller Profile

    ![A screenshot of choosing different profile.](img/interaction-profiles.png)

10. If the **Eye Gaze Interaction Profile**, or any other profile, appears with a yellow triangle next to it, select the triangle, and then in the **OpenXR Project Validation window**, click the **Fix** button. When you're finished, close the **OpenXR Project Validation window**

    ![A screenshot of fixing Eye Gaze.](img/eye-gaze-fix.png)

11. Click the **Depth Submission Mode** drop down and then select **Depth 16 Bit**.

    ![A screenshot of selecting depth 16 Bit.](img/depth.png)

## Configure MRTK3 Profile

1. In the **Project settings** window, click on the **MRTK3** option.

    ![A screenshot of selecting MRTK3 option.](img/mrtk-profile.png)

2. Click on the **circular icon** next to the profile field that says **None (MRTK Profile)** to assign the MRTK profile. In the **Select MRTK Profile** window that appears, click on the eye icon to show the hidden items. Then select the **MRTKProfile**.

    ![A screenshot of setting the MRTK profile](img/set-mrtk-profile.png)

3. After selecting the MRTKProfile, you may close the Select **MRTK Profile** window. Your MRTK3 section in the **Project Settings** should look like the image below.

    ![A screenshot of assigning MRTK profile.](img/assign-mrtk-profile.png)

    >**Note:**
    Once the MRTK settings are completed, the errors in the console can be cleared.

4. Click on the **Graphics** tab. In this window, next to **Lightmap Modes**, select the dropdown menu. Switch the value to **Custom** instead of **Automatic**. After this step, a list of modes should pop up. Double check that they are all marked as true, like the image below.  
    - Under the **Always Included Shaders** Section, make sure that the **Size** value is set to 6. This way we cut down on some shader elements to increase our performance.

    ![A screenshot of assigning MRTK profile.](img/set-lightmap-modes-to-custom.png)

5. Navigate to the **Quality** tab. You want to make sure that your Quality settings are set to **Low** for all platforms. You can use the arrows next to the **Default** bar to switch the checkmarks to be on the **Low** setting. 
    
    - The **Low** settings should be ready to go by default, but feel free to compare against the image below.

    ![A screenshot of setting up the Quality settings](img/set-quality-settings.png)

    >**Note:** Under the **Rendering** tab, check the **Universal Render Pipeline Asset** and see if you have an option to switch to **UniversalRP-LowQuality**. If you have that option, go ahead and switch over. If not leave it on the default Asset. 

## Create the Scene and Configure MRTK

1. In the menu bar, select **File** > **New Scene**.

2. Select the **Basic (Built-in)** and then click **Create**. Save the new scene with a name of your choice.

3. Delete the **main camera** from the scene. Leave the **Directional Light** in the scene, it will provide necessary lighting for several of our interactable objects.

4. Now, in the **project window**, search for **MRTK XR Rig** and **MRTK Input Simulator** and  drag and drop it to the **hierarchy** window. If your search results are not returning any items, ensure that you are searching for **All** items, as the search filter (usually located under the search bar) may be set to **In Assets** by default.  Configure the Transform component of each prefab as follows:

    - Position: X = 0, Y = 0, Z = 0
    - Rotation: X = 0, Y = 0, Z = 0
    - Scale: X = 1, Y = 1, Z = 1

        ![A screenshot of configure transform.](img/filter-all.png)

## Installing URP

1. In **Menu Bar** navigate to **Window** > **Package Manager** and install the latest version of **Universal Render Pipeline**, which may appear listed as **Universal RP**. If you created your Unity project with Universal Render Pipeline previously, then this package may already be installed.

2. Now to create the **URP pipeline asset**, in the **Project Window** right-click on the Assets folder and navigate to **Create** > **Rendering** > **Universal Render Pipeline** > **Pipeline Asset (Forward Renderer)**. The default name for this asset will be **UniveralRenderPipelineAsset**.

3. Configure the Project settings by navigating to **Edit** > **Project Settings** > **Graphics**. In **Scriptable Render Pipeline Settings**, click on the radio button and choose **Universal Render Pipeline Asset** (If you changed the default name of the asset in the previous step, then choose the asset with the name that you used in the previous step.).

## Import the Virtual Showroom Unity Package

To get started, first download the following **Unity Custom Package**: [MR_RetailShowroom](https://github.com/onginnovations/MR_RetailExperienceWorkshop/releases/download/v0.3/MS-Retail-Showroom-Optimized-Package-v3.0.unitypackage)

1. In the Unity menu, select **Assets** > **Import Package** > **Custom Package...**

2. In the **Import Package** window, select the custom unity package that you downloaded, and then select **Open**.

3. In the **Import Unity Package** windows, select the **All** button to ensure that all of the assets will be imported. Then select **Import**.

    >**Note:**
    You may clear or ignore any warnings that may appear during the import.

4. In the Assets folder, click on the **MR_RetailShowroom** folder, then open the **Prefab** folder and drag and drop the **Retail Dress Showroom** model into the **hierarchy** window and configure the transform component of this prefab as follows:

    - **Position**: X = 4.31, Y = -1.3, Z = 2.84
    - **Rotation**: X = 0, Y = 0, Z = 0
    - **Scale**: X = 0.12, Y = 0.12, Z = 0.12

     >**Note:**
     When in game mode, ignore the index out of range error as it appears recursively.
---
## [Next Section: Configure Your Virtual Showroom With Interactivity](3-configure-virtual-showroom.md) 