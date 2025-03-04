# <p align="center">
<img src="https://i.imgur.com/wURMIsq.jpeg" height="80%" width="80%" alt="Setting Up in Azure"/>
<br />

<h1>osTicket: Prerequisites and Installation</h1>

</p>

## Description

This project provides a comprehensive, step-by-step guide for implementing a scalable, open-source Help Desk solution using osTicket on Microsoft Azure.

It covers creating a Windows 10 VM, configuring a full web server environment (IIS, MySQL, PHP), and overcoming technical challenges with PHP modules, IIS permissions, and configuration conflicts.

The result is a documented process for creating a production-ready osTicket instance, demonstrating skills in system administration, web server configuration, and technical documentation.

Before you start, consider having an Azure account (with an active subscription) and basic knowledge of Azure (portal navigation, resource creation). To make it easier to reproduce this configuration, all the necessary installation files are available [here](https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0).
<br />

## Environments and Utilities Used

-   **Microsoft Azure**
-   **Virtual Machines**
-   **Remote Desktop Connection**
-   **Internet Information Services**
-   **MySQL**

## Operating Systems Used

-   **Windows 10**

## Index

1.  [Creating our virtual machine in Azure](https://github.com/HeidiBolivar/osticket-prereqs/edit/main/README.md#creating-our-virtual-machine-in-azure)
2.  [Establishing connection with the virtual machine implementing Remote Desktop Protocol](https://github.com/HeidiBolivar/osticket-prereqs/edit/main/README.md#establishing-connection-with-the-virtual-machine-implementing-remote-desktop-protocol)
3.  [Creating the environment for the ticketing system](https://github.com/HeidiBolivar/osticket-prereqs/edit/main/README.md#creating-the-environment-for-the-ticketing-system)
4.  [Adapting our web server](https://github.com/HeidiBolivar/osticket-prereqs/edit/main/README.md#adapting-our-web-server)
5.  [Setting up osTicket](https://github.com/HeidiBolivar/osticket-prereqs/edit/main/README.md#setting-up-osticket)

## Project Walk-through:

### Creating our virtual machine in Azure

1.  The first step is to navigate to the Microsoft Azure portal, which can be found [here](https://portal.azure.com/#home).<br/>

2.  Within the portal, locate the field titled "**Search resources, services, and docs (G+/)**" and enter the search term "**vm**". Click on "**Virtual machines**" in the resulting list.<br/>

    ![image](img/2.png)

3.  The following steps should be taken in order to create a virtual machine: firstly, click on "**Create**" > "**Azure virtual machine**".<br/>

    ![image](img/3.1.png)
    ![image](img/3.2.png)

4.  Then, click on "**Create new**" > click on the "**Name**" field > type "**osTicket**" > click on "**OK**".<br/>

    ![image](img/4.1.png)
    ![image](img/4.2.png)
    ![image](img/4.3.png)

5.  Assign a name to the VM by clicking on the "**Virtual machine name**" field and typing "**osticket-vm**".<br/>

    ![image](img/5.png)

6.  Click on "**Region settings**" and select "**East US 2**".<br/>

    ![image](img/6.1.png)
    ![image](img/6.2.png)

7.  Select the virtual machine image and choose the "**Windows 10 Pro, version 22H2 - x64 Gen2**" option.<br/>

    ![image](img/7.1.png)
    ![image](img/7.2.png)

8.  Click on the field marked as "**Username**". Here, a username must be typed and set up.<br/>

    ![image](img/8.png)

9.  Click on the field marked as "**Password**" and then enter and set up a password.<br/>

    ![image](img/9.png)

10. Click on the "**Confirm Password**" box and enter the password again.<br/>

    ![image](img/10.png)

11. The "**Licensing**" box must be checked.<br/>

    ![image](img/11.png)

12. Click on the option titled "**Review + Create**".<br/>

    ![image](img/12.png)

13. Following the conclusion of the review process, the subsequent step is to click the "**Create**" button.<br/>

    ![image](img/13.png)

<br/>

### Establishing connection with the virtual machine implementing Remote Desktop Protocol

14. Download [Microsoft Remote Desktop](https://apps.microsoft.com/detail/9wzdncrfj3ps?hl=es=EN&gl=EN). If you are using a Windows computer, look for "**Remote Desktop**" in the Applications list.<br/>

15. To establish a remote connection to the virtual machine, it is necessary to download this software to facilitate the process.<br/>

    ![image](img/15.png)

16. In the Azure Portal, click the search box, type "**VM**", and click "**Virtual Machines**".<br/>

    ![image](img/16.png)

17. Identify the "**public IP address**" of our virtual machine (`74.249.118.131`) and copy it by pressing `[[ctrl]]` + `[[c]]`.<br/>

    ![image](img/17.png)

18. Open "**Remote Desktop**".<br/>

    ![image](img/18.png)

19. Click "**Add**" > Click "**PC**" to enter our virtual machine information.<br/>

    ![image](img/19.1.png)
    ![image](img/19.2.png)

20. Click on "**Formal name or IP address**" and paste the IP address using `[[ctrl]]` + `[[v]]`.<br/>

    ![image](img/20.png)

21. Click the "**Display name**" section and enter a name for this PC.<br/>

    ![image](img/21.png)

22. Save the information.<br/>

    ![image](img/22.png)

23. Open your new PC.<br/>

    ![image](img/23.png)

<br/>

### Creating the environment for the ticketing system

24. Enter the username and password assigned to your virtual machine during Azure configuration and click **Connect**.<br/>

    ![image](img/24.png)

25. Configuring the virtual machine windows.<br/>

    ![image](img/25.png)

26. Open "**Microsoft Edge**" on the virtual machine.<br/>

    ![image](img/26.png)

27. Download [osTicket-Installation-Files.zip](https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0). This is an archive containing all the applications and dependencies required to install, configure, and run the ticketing system correctly.<br/>

    ![image](img/27.png)

28. Open "**File Explorer**".<br/>

    ![image](img/28.png)

29. Open the "**Download**" folder.<br/>

    ![image](img/29.png)

30. Extract "**osTicket-Installation-Files**".<br/>

    ![image](img/30.png)

31. Open "**Control panel**".<br/>

    ![image](img/31.png)

32. Click "**Uninstall**", then click "**Turn Windows features on or off**".<br/>

    ![image](img/32.1.png)
    ![image](img/32.2.png)

33. Enable the "**CGI**" feature.<br/>

    ![image](img/33.png)

34. We can test that the web server is installed correctly by entering the loopback IP (`127.0.0.1`) in the web browser, and this page should load.<br/>

    ![image](img/34.png)

35. Navigate to the "**osTicket-Installation-Files**" folder in File Explorer.<br/>

    ![image](img/35.png)

36. Install PHP Manager for IIS Setup: "**PHPManagerForIIS_V1.5.0**".<br/>

    ![image](img/36.png)

37. Install the IIS URL Rewrite module: "**rewrite_amd64_en-US**".<br/>

    ![image](img/37.png)

38. Create a folder called "**PHP**" in "**C:\\**".<br/>

    ![image](img/38.png)

39. Extract "**php-7.3.8-nts-Win32-VC15-x86**" to the "**PHP**" folder.<br/>

    ![image](img/39.png)

40. Download Microsoft Visual C++: "**VC_redist.x86**".<br/>

    ![image](img/40.png)

41. Download MySQL: "**mysql-5.5.62-win32**", selecting the "**typical**" configuration.<br/>

    ![image](img/41.1.png)
    ![image](img/41.2.png)

42. Select the "**Standard**" option.<br/>

    ![image](img/42.png)

43. Click the "**Next**" button.<br/>

    ![image](img/43.png)

44. Click the "**Next**" button.<br/>

    ![image](img/44.png)

45. Set up your credentials.<br/>

    ![image](img/45.png)

46. Click the "**Finish**" button.<br/>

    ![image](img/46.png)

<br/>

### Adapting our web server

47. Open "**IIS**" as an administrator.<br/>

    ![image](img/47.png)

48. Go to "**PHP Manager**".<br/>

    ![image](img/48.png)

49. Click "**Register new PHP version**".<br/>

    ![image](img/49.png)

50. Click "`...`".<br/>

    ![image](img/50.png)

51. Go to "**C:\\PHP**" and open "**php-cgi**".<br/>

    ![image](img/51.png)

52. Stop and start the server.<br/>

    ![image](img/52.png)

53. Extract "**osTicket-v1.15.8**".<br/>

    ![image](img/53.png)

54. Cut the folder "**Upload**".<br/>

    ![image](img/54.png)

55. Paste it into "**C:\\inetpub\\wwwroot**".<br/>

    ![image](img/55.png)

56. Rename "**upload**" to "**osTicket**".<br/>

    ![image](img/56.png)

57. Stop the server and restart it one more time.<br/>

    ![image](img/57.png)

58. Go to the "**osTicket**" folder.<br/>

    ![image](img/58.png)

59. Click "**Browse *:80 (http)**" on the right-hand side.<br/>

    ![image](img/59.1.png)

    This page should open:<br/>

    ![image](img/59.2.png)

60. Go to the "**osTicket > PHP Manager**" section.<br/>

    ![image](img/60.png)

61. Click on the "**Enable or disable extension**" button.<br/>

    ![image](img/61.png)

62. Enable "**php_imap.dll**", "**php_intl.dll**", and "**php_opcache.dll**".<br/>

    ![image](img/62.png)

63. Refresh the osTicket page and note the changes here.<br/>

    ![image](img/63.png)

64. In "**C:\\inetpub\\wwwroot\\osTicket\\include**", change the file "**ost-sampleconfig.php**" to "**ost-config.php**".<br/>

    ![image](img/64.png)

65. Enter the properties of the "**ost-config.php**" file.<br/>

    ![image](img/65.png)

66. Press the "**Security**" button.<br/>

    ![image](img/66.png)

67. Click on "**Advanced**".<br/>

    ![image](img/67.png)

68. Remove all inherited permissions from this object.<br/>

    ![image](img/68.png)

69. Click the "**Add**" button.<br/>

    ![image](img/69.png)

70. Click on "**Select a principal**".<br/>

    ![image](img/70.png)

71. Click here and type in "**Everyone**".<br/>

    ![image](img/71.png)

72. Click on the "**Check names**" button.<br/>

    ![image](img/72.png)

73. Press "**OK**".<br/>

    ![image](img/73.png)

74. Click on "**Full control**".<br/>

    ![image](img/74.png)

75. Click "**OK**".<br/>

    ![image](img/75.png)

76. Click the "**Apply**" button.<br/>

    ![image](img/76.png)

77. Press "**OK**".<br/>

    ![image](img/77.png)

78. Click "**OK**".<br/>

    ![image](img/78.png)

79. On the osTicket web page, click "**Continue**".<br/>

    ![image](img/79.png)

<br/>

### Setting up osTicket

80. Fill in the "**Admin user**" and "**System settings**" fields.<br/>

    ![image](img/80.png)

81. Before establishing the database, connecting to it using HeidiSQL is necessary. **Install HeidiSQL** and retain the default settings.<br/>

    ![image](img/81.png)

82. In HeidiSQL, click on "**New**".<br/>

    ![image](img/82.png)

83. Type in your root password (the password from the MySQL setup).
    
    ![image](img/83.png)
    
84.  Click the "**Open**" button.<br/>
    
     ![image](img/84.png)
    
85. Click on "**Database**".<br/>

    ![image](img/85.png)

86. Type "**osTicket**" and click "**OK**".<br/>

    ![image](img/86.png)

87. Fill in the "**Database settings**" field.<br/>

    ![image](img/87.png)

88. Click "**Install**".<br/>

    ![image](img/88.png)

<br/>

## Successfully Installed osTicket! What"s Next?

**By following the steps outlined in this comprehensive guide, you have now successfully installed osTicket and have it ready to use! But the setup doesn't end here. osTicket is now installed and ready for use! In the next project, I will extend this foundation by providing a detailed walkthrough on configuring agents (including their permissions and access levels), managing users, and exploring other key configuration options to tailor osTicket to specific support workflows.**

Next: [osTicket: Post-Installation Configuration](https://github.com/HeidiBolivar/post-install-config)
</b>

Thank you 😊 for taking the time to explore 🔎 this project, it's great to see someone so engaged and curious 💡. Connect with me on [LinkedIn](https://www.linkedin.com/in/heidibolivar/) 🤝 and let's see what we can build together ✨.
<br/>
<br/>
