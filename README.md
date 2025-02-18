# <p align="center">
<img src="https://i.imgur.com/wURMIsq.jpeg" height="80%" width="80%" alt="Setting Up in Azure"/>
<br />

<h1>osTicket: Prerequisites and Installation</h1>


<h2>Description</h2>

This project provides a comprehensive, step-by-step guide for implementing a scalable, open-source Help Desk solution using osTicket on Microsoft Azure. 

It covers creating a Windows 10 VM, configuring a full web server environment (IIS, MySQL, PHP), and overcoming technical challenges with PHP modules, IIS permissions, and configuration conflicts. 

The result is a documented process for creating a production-ready osTicket instance, demonstrating skills in system administration, web server configuration, and technical documentation. 

Before you start consider having an Azure account (with an active subscription), basic knowledge of Azure (portal navigation, resource creation). To make it easier to reproduce this configuration, all the necessary installation files are available [here.](https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0) 
<br />


<h2>Environments and Utilities Used</h2>

- <b>Microsoft Azure</b>
- <b>Virtual Machines</b>
- <b>Remote Desktop Connection</b>
- <b>Internet Information Services</b>
- <b>MySQL</b>


<h2>Operating Systems Used </h2>

- <b>Windows 10</b>

<h2>Index</h2>

1. [Creating our virtual machine in Azure](https://github.com/HeidiBolivar/osticket-prereqs/edit/main/README.md#create-a-virtual-machine-in-azure)
2. [Establishing connection with the virtual machine implementing Remove Desktop Protocol](https://github.com/HeidiBolivar/osticket-prereqs/edit/main/README.md#establishing-connection-with-the-virtual-machine-implementing-remove-desktop-protocol)
3. [Creating the environment for the ticketing system](https://github.com/HeidiBolivar/osticket-prereqs/edit/main/README.md#creating-the-environment-for-the-ticketing-system)
4. [Adapting our web server](https://github.com/HeidiBolivar/osticket-prereqs/edit/main/README.md#adapting-our-web-server)
5. [Setting up osTicket](https://github.com/HeidiBolivar/osticket-prereqs/edit/main/README.md#setting-up-osticket)


<h2>Project Walk-through:</h2>

<h3>Creating our virtual machine in Azure</h3>

1. The first step is to navigate to the Microsoft Azure portal, which can be found [here.](https://portal.azure.com/#home)<br/>
<br />
   
2. Within the portal, locate the field entitled "Search resources, services, and docs (G+/)", and enter the search term "vm". Click on "Virtual machines" in the resulting list <br/>
   
![image](img/2.png)
<br />

3. The following steps should be taken in order to create a virtual machine: firstly, click on "Create" > "Azure virtual machine".
   
![image](img/3.1.png)
![image](img/3.2.png)
<br />

4. Then, click on "Create new" > click on the "Name" field > type "osTicket" > click on "OK".

![image](img/4.1.png)
![image](img/4.2.png)
![image](img/4.3.png)
<br />

5. Assign a name to the VM by clicking on the "Virtual machine name" field and typing "osticket-vm".

![image](img/5.png)
<br />
    
6. Click on "Region settings" and select "East US 2".

![image](img/6.1.png)
![image](img/6.2.png)
<br />

7. Select the virtual machine image and choose the 'Windows 10 Pro, version 22H2 - x64 Gen2' option

![image](img/7.1.png)
![image](img/7.2.png)
<br />

8. Click on the field marked 'Username'. Here, a username must be typed and set up.
   
![image](img/8.png)
<br />

9. Click on the field marked 'Password' and then enter and set up a password.
 
![image](img/9.png)
<br />

10. Click on the 'Confirm Password' box and enter the password again

![image](img/10.png)
<br />

11. The 'Licensing' box must be selected.

![image](img/11.png)
<br />

12. Click on the option entitled 'Review + Create'.
 
![image](img/12.png)
<br />

13. Following the conclusion of the review process, the subsequent step is to click the "Create" button.

![image](img/13.png)
<br />
<br />

<h3>Establishing connection with the virtual machine implementing Remove Desktop Protocol</h3>

14. Download [Microsoft Remote Desktop](https://apps.microsoft.com/detail/9wzdncrfj3ps?hl=es=EN&gl=EN). If you are using a Windows computer, look for Remote Desktop in the Applications list.<br/>
<br />

15. To establish a remote connection to the virtual machine, it is necessary to download this software to facilitate the process.

![image](img/15.png)
<br />

16. In the Azure Portal, click the search box, type VM, and click Virtual Machines

![image](img/16.png)
<br />

17. Identify the public IP address of our virtual machine ("74.249.118.131") and copy it by pressing [[ctrl]] + [[c]]

![image](img/17.png)
<br />

18. Open "Remote Desktop"

![image](img/18.png)
<br />

19. Click Add > Click PC to introduce our virtual machine information

![image](img/19.1.png)
![image](img/19.2.png)
<br />

20. Click on "Formal name or IP address" and paste the IP address using [[ctrl]] + [[v]]

![image](img/20.png)
<br />

21. Click the Display name section and enter a name for this PC

![image](img/21.png)
<br />

22. Save the information

![image](img/22.png)
<br />

23. Open your new PC

![image](img/23.png)
<br />
<br />

<h3>Creating the environment for the ticketing system</h3>

24. Enter the username and password assigned to your virtual machine during Azure configuration and click Connect.

![image](img/24.png)
<br />

25. Configuring the virtual machine windows

![image](img/25.png)
<br />

26. Open Microsoft Edge on the virtual machine

![image](img/26.png)
<br />

27. Download [osTicket-Installation-Files.zip](https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0), this is an archive containing all the applications and dependencies required to install, configure and run the ticketing system correctly.

![image](img/27.png)
<br />

28. Open "File Explorer"

![image](img/28.png)
<br />

29. Open "Download folder" 

![image](img/29.png)
<br />

30. Extract "osTicket-Installation-Files"

![image](img/30.png)
<br />

31. Open "Contol panel"

![image](img/31.png)
<br />

32. Click 'Uninstall', then click 'Turn Windows features on or off' 

![image](img/32.1.png)
![image](img/32.2.png)
<br />

33. Enable CGI feature

![image](img/33.png)
<br />

34. We can test that the web server is installed correctly by entering the loopback IP (127.0.0.1) in the web browser and this page should load

![image](img/34.png)
<br />

35. Navigate to the 'osTicket-Installation-Files' folder in File Explorer.

![image](img/35.png)
<br />

36. Install PHP Manager for IIS Setup: "PHPManagerForIIS_V1.5.0"

![image](img/36.png)
<br />

37. Install the IIS URL Rewrite module: "rewrite_amd64_en-US"

![image](img/37.png)
<br />

38. Create a folder called "PHP" in "C:\"

![image](img/38.png)
<br />

39. Extract "php-7.3.8-nts-Win32-VC15-x86" to the 'PHP' folder

![image](img/39.png)
<br />

40. Download Microsoft Visual C++: "VC_redist.x86"

![image](img/40.png)
<br />

41. Download MySQL: "mysql-5.5.62-win32", selecting the "typical" configuration

![image](img/41.1.png)
![image](img/41.2.png)
<br />
<br />

42. Select the Standard option

![image](img/42.png)
<br />

43. Click the 'Next' button

![image](img/43.png)
<br />

44. Click the 'Next' button

![image](img/44.png)
<br />

45. Set up your credentials

![image](img/45.png)
<br />

46. Click the 'Finish' button

![image](img/46.png)
<br />
<br />

<h3>Adapting our web server</h3>

47. Open IIS as an administrator

![image](img/47.png)
<br />

48. Go to PHP Manager

![image](img/48.png)
<br />

49. Click "Register new PHP version"
    
![image](img/49.png)
<br />

50. Click here.

![image](img/50.png)
<br />

51. Go to "C:\PHP" and open "php-cgi"

![image](img/51.png)
<br />

52. Stop and start the server

![image](img/52.png)
<br />

53. Extract "osTicket-v1.15.8"

![image](img/53.png)
<br />

54. Cut the folder "Upload"

![image](img/54.png)
<br />

55. Paste it into "C:\inetpub\wwwroot"

![image](img/55.png)
<br />

56. Rename ‘upload’ to ‘osTicket’.

![image](img/56.png)
<br />

57. Stop the server and restart it one more time

![image](img/57.png)
<br />

58. Go to the osTicket folder

![image](img/58.png)
<br />

59.  Click Browse *80 (http) on the right-hand side

![image](img/59.1.png)
<br />

This page should open:

![image](img/59.2.png)
<br />

60. Go to the osTicket > PHP Manager section

![image](img/60.png)
<br />

61. Click on the 'Enable or disable extension' button

![image](img/61.png)
<br />

62. Enable "php_imap dll", "php_intl dll" and "php_opcache dll"

![image](img/62.png)
<br />

63. Refresh the osTicket page and note the changes here

![image](img/63.png)
<br />

64. In "C:\inetpub\wwwroot\osTicket\include" change file "ost-sampleconfig.php" to "ost-config.php"

![image](img/64.png)
<br />

65. Entry in the properties of the 'ost-config.php' file

![image](img/65.png)
<br />

66. Press 'Security' button

![image](img/66.png)
<br />

67. Click on 'Advanced' 

![image](img/67.png)
<br />

68. Remove all inherited permissions from this object

![image](img/68.png)
<br />

69. Click the 'Add' button

![image](img/69.png)
<br />

70. Click on "Select a principal"

![image](img/70.png)
<br />

71. Click here and type in 'Everyone

![image](img/71.png)
<br />

72. Click on the 'Check names' button

![image](img/72.png)
<br />

73. Press 'OK'

![image](img/73.png)
<br />

74. Click on 'Full control'

![image](img/74.png)
<br />

75. Click 'OK'

![image](img/75.png)
<br />

76. Click the 'Apply' button

![image](img/76.png)
<br />

77. Press 'OK'

![image](img/77.png)
<br />

78. Click "OK"

![image](img/78.png)
<br />

79. On the osTicket web page, click "Continue"

![image](img/79.png)
<br />
<br />

<h3>Setting up osTicket</h3

80. Fill in the 'Admin user' and 'System settings' fields

![image](img/80.png)
<br />

81. Before establishing the database, it is necessary to connect to it using HeidiSQL. Install HeidiSQL and retain the default settings.

![image](img/81.png)
<br />

82. In HeidiSQL, click on 'New

![image](img/82.png)
<br />

83. Type in your root password (the password from the mySQL setup)
 
![image](img/83.png)
<br />
 
84. Click the 'Open' button

![image](img/84.png)
<br />

85. Click on 'Database'

![image](img/85.png)
<br />

86. Type "osTicket" and click "OK"

![image](img/86.png)
<br />

87. Fill in the "Database settings" field

![image](img/87.png)
<br />

88. Click 'Install'

![image](img/88.png)
<br />
<br />

<h2>Successfully Installed osTicket! What's Next?</h2>

<b>By following the steps outlined in this comprehensive guide, you have now successfully installed osTicket and have it ready to use! But the setup doesn't end here. osTicket is now installed and ready for use! In the next project, I will extend this foundation by providing a detailed walkthrough on configuring agents (including their permissions and access levels), managing users, and exploring other key configuration options to tailor osTicket to specific support workflows.

[Next: osTicket: Post-Installation Configuration](https://github.com/HeidiBolivar/post-install-config)
</b>
<br />
<br />
</p>
