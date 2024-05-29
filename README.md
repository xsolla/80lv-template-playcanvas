# Installation

In this section, you will learn how to download and import the project template into PlayCanvas. These steps will ensure the successful installation of the project so that you can start working with it.

1. Download the Archive

   Description: Download the archive with the template from the provided link given by the developer.

   Result: You will have the project file archive downloaded, ready for import into PlayCanvas.

2. Import the Project into PlayCanvas

   Description: Go to the PlayCanvas platform and import the downloaded archive.

   Steps:

   Click on the Import Project button.

   Result: The project from the archive will be loaded into PlayCanvas and will be available for further configuration.

3. Navigate to the Project Hierarchy

   Description: Open the loaded project and go to the object hierarchy to configure the main project parameters.

   Steps:

   Find and click on the root element in the hierarchy.

   Result: You will be able to edit the main project settings, including room and region parameters.

4. Set a Unique Room Name and Region

   Description: Set a unique room name and choose a region for proper multiplayer functionality.

   Steps:

   1. In the Environments script attributes, specify a unique room name (roomName).

   2. Choose a region from the available options:

      'Asia, Singapore': 'asia'

      'Australia, Melbourne': 'au'

      'Chinese Mainland (See Instructions) Shanghai': 'cn'

      'Canada, East Montreal': 'cae'

      'Europe, Amsterdam': 'eu'

      'India, Chennai': 'in'

      'Japan, Tokyo': 'jp'

      'South America, Sao Paulo': 'sa'

      'South Korea, Seoul': 'kr'

      'USA, East Washington': 'us'

      'USA, West San José': 'usw'

   Result: The multiplayer part of your project will function correctly in the selected region.

5. Generating a Unique Room Name Using the Browser

   Description: You can generate a unique room name (UID) using an online tool. This will ensure that each room name is unique and avoids conflicts.

   Steps:

   1. Open your web browser.

   2. Go to a UID generator website like https://www.uuidgenerator.net/.

   3. Click the button to generate a new UID.

   4. Copy the generated UID.

   5. Paste the UID into the roomName field in the Environments script attributes.

   Result: You will have a unique room name that can be used for your multiplayer game.

# Customizing the Loading Screen

In this section, you will learn how to customize the loading screen for your project. You can change the title and background image to give your project a unique look.

1. Open the Code Editor

   Description: Access the code editor to modify the loading screen settings.

   Steps:

   1. Go to the Code Editor.

   2. Open the Scripts/Loading/LoadingScreen.js file.

   3. Result: You will have access to the code responsible for displaying the loading screen.

2. Configure Loading Screen Parameters

   Description: Customize the appearance of the loading screen by changing the title and background image.

   Steps:

   1. Locate the lines of code containing the appTitle and bgImageUrl variables.

   2. Change the value of the appTitle variable to set a new title.

   3. Change the value of the bgImageUrl variable to set a new background image.

   Result: The loading screen will display the new title and background image.

   ```
   pc.script.createLoadingScreen(function (app) {
       const bgImageUrl = 'https://cdn.xsolla.net/cloud-gaming-bucket-prod/87825ff1-948f-44ed-beaf-a56217b986af.png';
       const appTitle = '80lv Metasites Template';
       // browser renmder conde
       app.on('preload:end', function () {
           app.off('preload:progress');
       });
       app.on('preload:progress', setProgress);
       app.on('start', hideLoader);
   });
   ```

   This code handles the application's preloading, and in the last line, the loader function hides the loading screen and starts the game. Everything that happens before that is drawn in the browser window using JS.

# Replacing the Scene and Adjusting Scale

In this section, you will learn how to replace the default scene and adjust the scale of objects in your project. These actions will allow you to configure the visual elements of your project according to your requirements.

1. Replace the Default Scene

   Description: Remove the default scene and add your own to change the project's content.

   Steps:

   1. Delete the default Sponza entity from the Root.

   2. Add your own scene.

   Result: The project will display the new scene instead of the default one.

2. Adjust Scale in the Editor

   Description: Adjust the scale of the new scene for optimal display in the project.

   Steps:

   1. In the editor's right menu, change the XYZ values of the Scale parameter.

   2. Observe the changes in real time.

   Result: The new scene will be displayed with the desired scale.

3. Adjust Character Scale

   Description: Change the character scale for correct display in the new scene.

   Steps:

   1. Find the PlayerModel entity (Users → User → PlayerModel).

   2. Change the scale values of the PlayerModel entity.

   Result: The character will be displayed in the new scene with the desired scale.

# Configuring Photon (additional step)

In this section, you will learn how to configure Photon to provide multiplayer and online chat in your project. Proper Photon setup will ensure stable network functionality.

1. Basic Photon Settings

   Description: Configure Photon for multiplayer and online chat in your project.

   Steps:

   1. Learn the basic Photon settings necessary for proper operation.

   2. Open the PhotonLoadBalancing.js script file in the code editor (Scripts → Network → PhotonLoadBalancing.js).

   Result: You will be able to configure the main Photon parameters, such as room name and region.

2. Change Settings in PhotonLoadBalancing.js

   Description: Change the Photon settings in the PhotonLoadBalancing.js file to synchronize with the project parameters. In the current version of the template, Photon is initialized in the PlayCanvas stream in the Before Engine hook, so you will need to set the roomName and region values manually as in step 4 of the Installation section.

   Steps:

   1. ind the PhotonLoadBalancing.js file in Assets (Scripts → Network → PhotonLoadBalancing.js).

   2. Click the Edit button to open the file in the code editor.

   3. Change the roomName and region values to the same ones specified in the Environments script.

   ```
   this.roomName = 'XSOLLA_ROOM';
   this.region = 'us';
   ```

   Result: The Photon settings will be synchronized with your project parameters, ensuring the correct operation of the multiplayer functionality.
