# Guide to install GLFW on Windows for C++
![GLFW logo](https://www.glfw.org/img/favicon/favicon-196x196.png "GLFW logo")
![C++ logo](https://upload.wikimedia.org/wikipedia/commons/thumb/1/18/ISO_C%2B%2B_Logo.svg/120px-ISO_C%2B%2B_Logo.svg.png "C++ logo")
![Windows logo](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e2/Windows_logo_and_wordmark_-_2021.svg/250px-Windows_logo_and_wordmark_-_2021.svg.png "Windows logo")


## Instructions

- Make sure you have installed the compiler that you will use for C++, in my case I will  use MinGW.

  ### Install MinGW on Windows

  Download the installer [here](https://sourceforge.net/projects/mingw/)

  I recommend you watch this video where they explain how to install it:

  [![Alt text](https://img.youtube.com/vi/WWTocqPrzMk/0.jpg)](https://www.youtube.com/watch?v=WWTocqPrzMk&t)

- Now install [CMake](https://cmake.org/), you can download the installer [here](https://github.com/Kitware/CMake/releases/download/v3.21.3/cmake-3.21.3-windows-x86_64.msi) or check the [download page](https://cmake.org/download/).

  When you finish installing CMake make sure the path is found in the environment variables.

  If you like to use the terminal you can use the following command to open the system properties window:

  ```sh
  PS C:\> start sysdm.cpl
  ```
  When the system properties window opens, click on the advanced options tab and then click on environment variables. Check in `system variables > Path` that the following path is found:
  ```
  C:\Program Files\CMake\bin
  ```

### Download GLFW

In this installation guide I will show you how to install GLFW from the `source package`, to download the source package click [here](https://github.com/glfw/glfw/releases/download/3.3.4/glfw-3.3.4.zip).

### Install GLFW

When the download is finished, unzip the folder in the path you want, for example on the desktop. Once the file is unzipped open the terminal in administrator mode.

![Run as administrator](https://www.wikihow.com/images/6/68/Run-Command-Prompt-As-an-Administrator-on-Windows-Step-4.jpg "wikiHow - How to Run Command Prompt As an Administrator on Windows")

In the terminal go to the path where to unzip the file
```sh
PS C:\path\to\glfw-version>
```

Once we are in the folder path we will use CMake, using the following commands:
```sh
PS C:\path\to\glfw-version> cmake . -G "MinGW Makefiles"
PS C:\path\to\glfw-version> cmake --build .
```

Before proceeding with the installation make sure to create the folder in the following path:
```
C:\Program Files (x86)\GLFW\include\GLFW
```

When you make sure that the path exists you can install using the following command:
```sh
PS C:\path\to\glfw-version> cmake --install . --default-directory-permissions u=rwx
```

# Run Example code
Now you can run the [Example code](https://www.glfw.org/documentation.html#:~:text=closed%20source%20software.-,Example%20code,-Below%20is%20a) from the GLFW documentation using CMake, check the [example folder](../master/example-code).
