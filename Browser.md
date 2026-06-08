<img width="352" height="170" alt="Image" src="https://github.com/user-attachments/assets/fa2fe68a-5662-4488-985b-ebcb2554fff3" />


### What **100% worked for me** on my Macbook 🔥:


1. Download both the **.jar** and **.dmg** (Apple Silicon) files of Burp Pro from here: [link](https://portswigger.net/burp/releases).
2. Download the loader from here: [link](https://raw.githubusercontent.com/xiv3r/Burpsuite-Professional/refs/heads/main/loader.jar).
3. Put Burp Pro's `.jar` file and `loader.jar` in the same directory, then run this command in Terminal to activate the license:

   ```
   java -jar loader.jar burpsuite_pro_v2025_[version].jar
   ```

   Follow the loader instructions to activate license (see the video at timestamp 2:44): [link](https://youtu.be/Gxyhk2vyGdw?t=164).
4. Once the license is installed, close both the Burp Pro `.jar` and `loader.jar`.
5. Install the **.dmg** (Apple Silicon) file you downloaded in step 1.
6. Open Finder, go to the Applications folder, right-click the **Burp Suite Professional.app** icon and choose **Show Package Contents**. Navigate to `Contents > Resources > app` and copy-paste the `loader.jar` file you downloaded in step 2 to this directory.
7. In Terminal, run:

   ```
   open -a TextEdit "/Applications/Burp Suite Professional.app/Contents/vmoptions.txt"
   ```

   and add the following lines at the end:

   ```
   --add-opens=java.base/java.lang=ALL-UNNAMED
   --add-opens=java.base/jdk.internal.org.objectweb.asm=ALL-UNNAMED
   --add-opens=java.base/jdk.internal.org.objectweb.asm.tree=ALL-UNNAMED
   --add-opens=java.base/jdk.internal.org.objectweb.asm.Opcodes=ALL-UNNAMED
   -javaagent:loader.jar
   -noverify
   ```
8. Finally, run:

   ```
   sudo xattr -r -d com.apple.quarantine /Applications/Burp\ Suite\ Professional.app
   ``` 
   - (This command typically produces **no output.**)
   
9. You’re done. Open the application normally from the Application Folder by clicking the burp's icon and make it 'keep in dock'  — the browser and response Render option should work.


<img width="1600" height="1040" alt="Image" src="https://github.com/user-attachments/assets/7c792c57-0546-4da0-9a72-e55bfa5c141f" />
