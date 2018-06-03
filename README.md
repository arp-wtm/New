# News2
UDACITY ABND project 7 <br>
This app is created to display a list of news stories, given from the guardian site.<br>
Each list item on the main screen displays relevant text and information about the story:<br>
- Title of news article
- Name of the section 
- Name of the author (if present)
- Date of publication
All this information are modeled with a custom class Article <br>
Clicking on a story uses an intent to open the story in the user’s browser.<br>
When there is no data to display, the app shows a default TextView that informs the user with "no data news found".<br>
The app checks whether the device is connected to the internet and responds appropriately. <br>
The result of the request is validated to account for a bad server response or lack of server response.<br>
If no connection or bad connection the message "no internet connection, check your device settings" is displayed to the user<br>
Networking operations are done using a NewsLoader, that perform the network request,<br>
parse the response, and extract the news articles in background thread.<br>
The Settings screen is for set preference of the user in displaying articles, 
order by:
newest,<br> oldest,<br> relevance.<br>
Closing the app will maintain the preference chosen.<br>
Return to main screen will update list with the new order set by user.<br>
## TEST
The code runs without errors on HUAWEI JMM-L22 Android 7.0 Api 24.<br>
The Android Project is built  for Phone and Tablet with LEVEL API 15: Android 4.0.3 (IceCreamSandwich)<br>
in QueryUtils class there is some commented code that needs to test spinner progress bar.<br> 
The message of no internet connection appeares if you test the app in airplaine mode.<br>
During the text, for some query there was an error with index 0 out of array, when i try to parse the author name<br>
from the JSONArray "tags". To resolve this problem  I use a parse in try catch, testing if array has length > 0 before get the String "web Title" that contains the name of the author.<br> If it return, I set the name of author to "missed author"
### build 
```
build.gradle dependencies {
    implementation fileTree(dir: 'libs', include: ['*.jar'])
    implementation 'com.android.support:appcompat-v7:27.1.1'
    compile 'com.android.support.constraint:constraint-layout:1.1.0'
    implementation 'com.android.support.constraint:constraint-layout:1.1.0'
    testImplementation 'junit:junit:4.12'
    androidTestImplementation 'com.android.support.test:runner:1.0.2'
    androidTestImplementation 'com.android.support.test.espresso:espresso-core:3.0.2'
}
```
### LICENCE 
 made by Antonella on may.31.2018<br>
 for news stage 2 app exercise for project 7<br>
 in Udacity ABND course. It uses as model the<br>
 Quake Report app of the lesson on JSON Parsing and Settings Preference that is under this licence:<br>

 Copyright (C) 2018 The Android Open Source Project<br>
 
 Licensed under the Apache License, Version 2.0 (the "License");<br>
 you may not use this file except in compliance with the License.<br>
 You may obtain a copy of the License at<br>
 
      http://www.apache.org/licenses/LICENSE-2.0
      
 Unless required by applicable law or agreed to in writing, software<br>
 distributed under the License is distributed on an "AS IS" BASIS,<br>
 WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.<br>
 See the License for the specific language governing permissions and<br>
 limitations under the License.


All news displayed come from https://open-platform.theguardian.com <br>
© 2016 Guardian News and Media Limited or its affiliated companies. All rights reserved.
