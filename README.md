# FIUFirendly -- Mobile Application <Updated Fall 2024>

Product Owners: AP


This is the first version of the FIUFirendly application. It was originally built in Fall of 2024 by AP for Florida International University's CEN 4010 - Group Project Course, and has been started for a group of student that are currently taking Soft engieneer class. FIUFirendly is a smartphone-based on current events application designed for students to get in touch with, it provides support in 3 different languages (English, Spanish & Haitian Creole). The main purpose of the application in its current state is to provide early and continued access to events that are currently happen in FIU.

The application provides the following features to its users:

- Important information about groups.
- Important information about special events.
- Information merge into one app.
- Better opportunities to get in touch with FIU students.
- Time to explore more adventures inside FIU.

---

### Project Structure

The following tree structure will be useful to visualize how the project is structured:

```

├── Code

│   └── FIUFriendly

│       ├── assets

│       │   ├── icons

│       │   └── images

│       ├── functions (Cloud functions that serve as an API that lives in the Cloud)

│       ├── node_modules (Inside here are all the modules installed after running ``npm install``)

│       └── src (This is where the actual code for each component and page of the application lies)

│           ├── Components

│           │   └── components

│           ├── JSON files

│           └── documents

├── Documentation

├── Posters

├── PresentationSlides

└── Videos

```

All the functionality lies in the `Code/FIUFriendly` directory. The rest of the directories that are in the root are solely for documentation purposes.

The root of the `FIUFriednly/src` directory is where all the source code for the application lies. The main entrypoint of the application is through `App.js`, which is where the application is created. To add new screens you must reference them in the `App.js` file and create a new navigation reference inside the navigators in this file.

Within the root of the `FIUFriendly` directory is a file called `package.json`, which defines the scripts that allows to run the application and contains meta-data about the project, in addition to defining the project dependencies.

### Installation & Running steps

To install NuMom, you will need to install Node.js and npm as your dependency manager first, available here: -- (https://nodejs.org/en/).

You must then clone the Github repository onto your local machine. You may do this in any file on your computer by doing `cd {file path}` command in your terminal before running the following clone command in your terminal as well.

```

git clone https://github.com/CEN40140W.git

```

After the repository is cloned, you must go into it by doing `cd moms-infants-healthy` in your terminal. Then run these commands in your terminal to install the necessary dependencies:

```

npm install --global expo-cli
npm install && expo install

```

Install the expo client on your mobile device or install the Android/Iphone simulator on your computer

iOS: https://apps.apple.com/app/apple-store/id982107779

Android: https://play.google.com/store/apps/details?id=host.exp.exponent&referrer=www

Finally, you will need to setup the Firebase API key to open the app locally. After this, the application should be ready to start using the command `expo start` in your command line. This will open a window where Expo will create a QR code on your computer that you can scan with the mobile Expo app to open the application on your smartphone. You may have to wait a minute while your project bundles and loads for the first time. If using a simulator to run the app on your computer, using `npm start` instead will show instructions on how to run it on the simulator.

### API Keys

Both the Firebase and Twilio API keys are provided by Eduardo, so contact him if you need them. For the Firebase API key, it should be a file called firebase_account.json. To set it up properly, move it into the /src/ folder of your local repository. The application will not start up properly without this API key in the correct place.

To gain access to the Twilio API for messaging users, you will need to navigate to the /functions/ folder and locate twilio_account.js. In that file you will need to edit the strings for accountSid and authToken to the account’s credentials and you will have access to the Twilio API.

### Accessing Firebase

To access Firebase, you will first have to install Firebase and its tools onto your machine. This can be done by running npm install --save firebase firebase-tools in your command line in the directory in which you would like to access firebase. Then, in the same directory you can deploy new functions using firebase deploy --project moms-and-infants-healthy.

### Deploying to Android

1. Login to the developer expo account by typing "expo login" in the terminal. You'll have to contact Eduardo to get his login credentials.

2. Increment the versionCode in app.json by 1.

3. Save app.json and close it.

4. Navigate to your project directory 'moms-infants-healthy' and build the apk in the terminal by entering: "expo build:android"

5. Choose “apk” and hit enter to build the app as an .apk file, the standard installation package for Android apps..
   You might encounter the error: “Connecting to metro bundler failed.” That's fine to ignore, just keep trying the build command until it starts the metro bundler. It may take a few attempts.

6. It will take a bit to build the apk but once it finishes, you'll be placed in a queue for your apk to build. You can go to the expo link in the terminal to monitor the build status while it finishes.

7. Download the apk once it finishes building and then login to the google play console. Again, you will need to contact Eduardo for the credentials.

8. Click on nuMom, then open testing. Once there, click on "Create new release"

9. Upload the apk file you just built to add it to the release. Click “save” and then “review release” to finish creating the new release.

You should also commit the version code change you did in the app.json to development on GitHub.

### Deploying to iOS

1. Install `eas-cli` globally: `npm install -g eas-cli`.

2. Increment the app version in app.json by 1 (ex. 0.5.0 -> 0.5.1).

3. Ensure you `src/firebase_account.json` is commented out from .gitignore file. Re-comment it back once you're done.

4. Navigate to your project directory 'moms-infants-healthy' and build the ipa in the terminal by entering: `npx eas build --platform ios`.

5. Login with the account's apple credentials.

6. It will take a bit to build the ipa but once it finishes, you'll be placed in a queue for your ipa to build. You can go to the expo link in the terminal to monitor the build status while it finishes.

7. Download the ipa once it finishes building.

8. Open Apple 'Transporter' app (you can download it on th apple app store) and upload the ipa file.

You should also commit the version code change you did in the app.json to development on GitHub.
