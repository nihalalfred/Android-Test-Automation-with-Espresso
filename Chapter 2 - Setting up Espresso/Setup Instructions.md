# Setup Instructions


## 1. Installing JAVA JDK

https://www.oracle.com/java/technologies/downloads/

**(jdk 18 - Note: you need to create or login to download)** 

- Once downloaded and extracted, open terminal and view the file by using
the command open /Library/Java/JavaVirtualMachines

- Export `$JAVA_Home` variable in our profile.

`vi ~/.zshrc` (to open the profile for editing with “vi”)

- Use `:` Write to edit the file
- Add the following line:

`export JAVA_HOME=/Library/Java/JavaVirtualMachines/<name-of-your-jdk-folder>/Contents/Home`

- Use `esc` to go back to normal mode

- Use `:wq` to save and quit back to terminal

- To save the changes run the following command: 

`source ~/.zshrc`

- To verify if java version is correct run the following commands:

`java -version`

`javac -version`

## 2. Installing Gradle

> Gradle is a build tool with a focus on build automation and support for multi-language development.

- Use Homebrew to install gradle

- If you don’t have Homebrew installed on your mac you can download the installation script from
here 

(run this command in your terminal):
 
 `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`

- Once Homebrew  installation is successful run the following command: 

`brew install gradle`

- Confirm the installation by running the following command: 

`gradle-v`

## 3. Installing Android Studio:

https://developer.android.com/studio
