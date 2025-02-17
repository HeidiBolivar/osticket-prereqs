# <p align="center">
<img src="https://i.imgur.com/wURMIsq.jpeg" height="80%" width="80%" alt="Setting Up in Azure"/>
<br />

<h1>osTicket: Prerequisites and Installation</h1>


<h2>Description</h2>

This project provides a comprehensive, step-by-step guide for implementing a scalable, open-source Help Desk solution using osTicket on Microsoft Azure. 

It covers creating a Windows 10 VM, configuring a full web server environment (IIS, MySQL, PHP), and overcoming technical challenges with PHP modules, IIS permissions, and configuration conflicts. 

The result is a documented process for creating a production-ready osTicket instance, demonstrating skills in system administration, web server configuration, and technical documentation. 

To facilitate reproducing this setup, all necessary installation files are available [here.](https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0)
<br />


<h2>Environments and Utilities Used</h2>

- <b>Microsoft Azure</b>
- <b>Virtual Machines</b>
- <b>Remote Desktop Connection</b>
- <b>Internet Information Services</b>
- <b>MySQL</b>


<h2>Operating Systems Used </h2>

- <b>Windows 10</b>

<h2>Project Walk-through:</h2>


1. The first step is to navigate to the Microsoft Azure portal, which can be found at the following URL: https://portal.azure.com/#home <br/>
<br />
<br />
   
2. Within the portal, locate the field entitled "Search resources, services, and docs (G+/)", and enter the search term "vm". Click on "Virtual machines" in the resulting list <br/>
   
![image](https://github.com/user-attachments/assets/2b7a84ad-27e0-4e4d-9af3-cd483c19a931)
<br />
<br />

3. The following steps should be taken in order to create a virtual machine: firstly, click on "Create" > "Azure virtual machine".
   
![image](https://github.com/user-attachments/assets/048b2122-1b05-4fb0-9081-52f67b319b50) ![image](https://github.com/user-attachments/assets/504c1c93-71d7-4694-87c7-fc2d83f5b241)
<br />
<br />

4. Then, click on "Create new" > click on the "Name" field > type "osTicket" > click on "OK".

![image](https://github.com/user-attachments/assets/f750cd40-d420-48ba-a679-fbca3ed602a1)
![image](https://github.com/user-attachments/assets/f7790b2b-40f8-4734-8a69-fc5b90e913f9)
![image](https://github.com/user-attachments/assets/2153655a-5f2a-4bf3-a9b9-565ca7011e6f)
<br />
<br />

5. Assign a name to the VM by clicking on the "Virtual machine name" field and typing "osticket-vm".

![image](https://github.com/user-attachments/assets/3a225c49-ef72-451f-842a-0a9eebdb9f68)
<br />
<br />
    
6. Click on "Region settings" and select "East US 2".

![image](https://github.com/user-attachments/assets/e1083791-f708-477d-84db-980d4583ccb0)
![image](https://github.com/user-attachments/assets/e3bd9a7e-41dc-4a0c-b41d-2e498d37ba29)
<br />
<br />

7. Select the virtual machine image and choose the 'Windows 10 Pro, version 22H2 - x64 Gen2' option

![image](https://github.com/user-attachments/assets/63d900b9-45b8-4a11-a72f-caf8c45010f1)
![image](https://github.com/user-attachments/assets/8b1ec940-3fef-41e3-b841-435169e87ba6)
<br />
<br />

8. Click on the field marked 'Username'. Here, a username must be typed and set up.
   
![image](https://github.com/user-attachments/assets/581e23da-5a05-426f-bd4b-b81a01ff05bc)
<br />
<br />

9. Click on the field marked 'Password' and then enter and set up a password.
 
![image](https://github.com/user-attachments/assets/b12f5e22-2251-4119-9399-7f78390be978)
<br />
<br />

10. Click on the 'Confirm Password' box and enter the password again

![image](https://github.com/user-attachments/assets/93cd4429-d26f-48e4-b52e-43392fca2e93)
<br />
<br />

11. The 'Licensing' box must be selected.

![image](https://github.com/user-attachments/assets/d0f1ad80-5a2a-496b-b643-3244c9fe019c)
<br />
<br />

12. Click on the option entitled 'Review + Create'.
 
![image](https://github.com/user-attachments/assets/0d84542d-d6ab-4c32-b49a-7513e655f92a)
<br />
<br />

13. Following the conclusion of the review process, the subsequent step is to click the "Create" button.

![image](https://github.com/user-attachments/assets/5b255fa6-7666-4026-8084-be0cd4f5985b)
<br />
<br />

14. Navigate to the following URL: https://apps.microsoft.com/detail/9wzdncrfj3ps?hl=es=EN&gl=EN 

15. To establish a remote connection to the virtual machine, it is necessary to download this software to facilitate the process.

![image](https://github.com/user-attachments/assets/ac143ba3-98f1-49da-8ee9-d66d938718b3)
<br />
<br />

16. In the Azure Portal, click the search box, type VM, and click Virtual Machines

![image](https://github.com/user-attachments/assets/2fe8ca65-ea2c-4979-afef-0c034778a781)
<br />
<br />

17. Identify the public IP address of our virtual machine ("74.249.118.131") and copy it by pressing [[ctrl]] + [[c]]

![image](https://github.com/user-attachments/assets/9d8f5719-c03a-46f0-880b-4d633b57594a)
<br />
<br />

18. Open "Remote Desktop"

![image](https://github.com/user-attachments/assets/f878d7cf-d995-4093-8ad6-bbcf63903af6)
<br />
<br />

19. Click Add > Click PC to introduce our virtual machine information

![image](https://github.com/user-attachments/assets/faeafb40-8424-47a2-b2f4-fe3bbdb3a50a)
![image](https://github.com/user-attachments/assets/9fb9ed79-5c45-495e-a20b-a36accbdc1c4)
<br />
<br />

20. Click on "Formal name or IP address" and paste the IP address using [[ctrl]] + [[v]]

![image](https://github.com/user-attachments/assets/3c325d20-b250-4ddd-95dd-12dcceacc471)
<br />
<br />

21. Click the Display name section and enter a name for this PC

![image](https://github.com/user-attachments/assets/1f57ab7e-6af2-4343-8dfa-4289f1ed6b72)
<br />
<br />

22. Save the information

![image](https://github.com/user-attachments/assets/5f152241-7aef-474b-8b85-ceadaf8437d7)
<br />
<br />

23. Open your new PC

![image](https://github.com/user-attachments/assets/8f0d4836-da7e-44ea-b677-a68becffcdf3)
<br />
<br />

24. Enter the username and password assigned to your virtual machine during Azure configuration and click Connect.

![image](https://github.com/user-attachments/assets/80eda1c9-bad2-4d96-9c11-ac4c9cc8f024)
<br />
<br />

25. Configuring the virtual machine windows

![image](https://github.com/user-attachments/assets/3d50eff5-e924-48c3-8d89-a4e072ba06f5)
<br />
<br />

26. Open Microsoft Edge on the virtual machine

![image](https://github.com/user-attachments/assets/5b165075-4e39-4182-b2d3-3620b5d21cc5)
<br />
<br />

27. Download [osTicket-Installation-Files.zip](https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0), this is an archive containing all the applications and dependencies required to correctly install, configure and run the ticketing system.

![image](https://github.com/user-attachments/assets/25a0b084-6b5f-4925-8059-6ba5bedad582)
<br />
<br />

28. Open "File Explorer"

![image](https://github.com/user-attachments/assets/4884439a-61fc-47b0-a312-b94cc8553c7f)
<br />
<br />

29. Open "Download folder" 

![image](https://github.com/user-attachments/assets/6b0652d2-ca8a-4944-bd70-290fcb49eda8)
<br />
<br />

30. Extract "osTicket-Installation-Files"

![image](https://github.com/user-attachments/assets/45175424-803d-4d7d-a2d0-130aa22406e4)
<br />
<br />

31. Open "Contol panel"

![image](https://github.com/user-attachments/assets/19e39c2a-4de9-4f2d-b30e-6da4eb029db6)
<br />
<br />

32. CClick 'Uninstall', then click 'Turn Windows features on or off' 

![image](https://github.com/user-attachments/assets/69e4da06-73f7-4210-9c7e-3dac3df0173a)
![image](https://github.com/user-attachments/assets/0dc12598-b47c-4cbd-aef4-957b8025f917)
<br />
<br />

33. Enable CGI feature

![image](https://github.com/user-attachments/assets/be0beca4-49a2-4c60-a36b-49c31b60b3c7)
<br />
<br />

34. We can test that the web server is installed correctly by entering the loopback IP (127.0.0.1) in the web browser and this page should load

![image](https://github.com/user-attachments/assets/8ee9797f-35c2-4841-a183-270e235a431b)
<br />
<br />

35. Navigate to the 'osTicket-Installation-Files' folder in File Explorer.

![image](https://github.com/user-attachments/assets/2ee08d0e-bd7e-4612-a8bb-1469146d57ee)
<br />
<br />

36. Install PHP Manager for IIS Setup: "PHPManagerForIIS_V1.5.0"

![image](https://github.com/user-attachments/assets/2658f29f-ebb6-49a7-84d6-4cb7c89a8a20)
<br />
<br />

37. Install the IIS URL Rewrite module: "rewrite_amd64_en-US"

![image](https://github.com/user-attachments/assets/7772b542-6a82-44a5-934a-d446002b3be0)
<br />
<br />

38. Create a folder called "PHP" in "C:\"

![image](https://github.com/user-attachments/assets/35603018-9fe6-4070-8878-22fe6ca052c1)
<br />
<br />

39. Extract "php-7.3.8-nts-Win32-VC15-x86" to the 'PHP' folder

![image](https://github.com/user-attachments/assets/40f885f3-520a-4b86-9d0b-3dc027f3ed8a)
<br />
<br />

40. Download Microsoft Visual C++: "VC_redist.x86"

![image](https://github.com/user-attachments/assets/3f08029b-c496-4e85-80b5-64b55da069d7)
<br />
<br />

41. Download MySQL: "mysql-5.5.62-win32", selecting the "typical" configuration

![image](https://github.com/user-attachments/assets/f22d0253-6007-4bc7-a2c1-8ed901023359)
![image](https://github.com/user-attachments/assets/5f1c660b-5913-479e-be5b-ed789a38b335)
<br />
<br />

42. Select the Standard option

![image](https://github.com/user-attachments/assets/372c99f6-44b5-45b1-a68b-1e0f51a38642)
<br />
<br />

43. Click the 'Next' button

![image](https://github.com/user-attachments/assets/611f1040-d9e2-4382-acb4-15d3ea53a6fb)
<br />
<br />

44. Click the 'Next' button

![image](https://github.com/user-attachments/assets/23e9b359-5287-458d-9ca1-ab325849a6f1)
<br />
<br />

45. Set up your credentials

![image](https://github.com/user-attachments/assets/9356150b-3b5f-4bd3-9e1a-a28a6f0f08d9)
<br />
<br />

46. Click the 'Finish' button

![image](https://github.com/user-attachments/assets/23f7531a-1e1d-40c6-91f8-ad547e321d0d)
<br />
<br />

47. Open IIS as an administrator

![image](https://github.com/user-attachments/assets/6d19c17a-541e-44c2-ad9a-f3ecb924a173)
<br />
<br />

48. Go to PHP Manager

![image](https://github.com/user-attachments/assets/eccebfdf-4075-4c21-84c7-2140e9a44821)
<br />
<br />

49. Click "Register new PHP version"
    
![image](https://github.com/user-attachments/assets/1d6eb94f-f5e5-4abc-8b8d-6949c9fa77f7)
<br />
<br />

50. Click here.

![image](https://github.com/user-attachments/assets/96463a17-a2ae-4a82-8b3e-eff677913de0)
<br />
<br />

51. Go to "C:\PHP" and open "php-cgi"

![image](https://github.com/user-attachments/assets/68f84604-4d26-48e7-b3fc-7f1aa87fe27f)
<br />
<br />

52. Stop and start the server

![image](https://github.com/user-attachments/assets/981a0988-8908-403a-bc32-61c59db08bfe)
<br />
<br />

53. Extract "osTicket-v1.15.8"

![image](https://github.com/user-attachments/assets/141e1111-dcac-4c36-a14a-9e2a1227e484)
<br />
<br />

54. Cut the folder "Upload"

![image](https://github.com/user-attachments/assets/0a76c050-7464-4c5b-a88f-dd0fbafa7a62)
<br />
<br />

55. Paste it into "C:\inetpub\wwwroot"

![image](https://github.com/user-attachments/assets/1502f18b-3ac5-4613-91ab-ad8cdcdada2a)
<br />
<br />

56. Rename ‘upload’ to ‘osTicket’.

![image](https://github.com/user-attachments/assets/26b0b729-d240-4db1-9c2e-d637ccd147f2)
<br />
<br />

57. Stop the server and restart it one more time

![image](https://github.com/user-attachments/assets/a7548cf9-cd34-48bc-9457-84da31303a59)
<br />
<br />

58. Go to the osTicket folder

![image](https://github.com/user-attachments/assets/06c0aad2-09a1-4391-ae14-496fd89f1cd8)
<br />
<br />

59.  Click Browse *80 (http) on the right-hand side

![image](https://github.com/user-attachments/assets/b39cfd41-ff9e-4cfb-a3bc-ee4b3a6ba646)
<br />
<br />

This page should open:

![image](https://github.com/user-attachments/assets/16b0795b-1095-4a63-8dc6-067bff19ec27)
<br />
<br />

60. Go to the osTicket > PHP Manager section

![image](https://github.com/user-attachments/assets/eb8d6fca-9acb-43f2-bd36-caf0ecb02a45)
<br />
<br />

61. Click on the 'Enable or disable extension' button

![image](https://github.com/user-attachments/assets/6f1366fe-dce7-4a33-bacd-e3b5a6322600)
<br />
<br />

62. Enable "php_imap dll", "php_intl dll" and "php_opcache dll"

![image](https://github.com/user-attachments/assets/52f7424f-7d66-43b0-8b0f-c8cef9e75a8d)
<br />
<br />

63. Refresh the osTicket page and note the changes here

![image](https://github.com/user-attachments/assets/41008ce8-e034-4f5a-8c0b-69c8022aff94)
<br />
<br />

64. In "C:\inetpub\wwwroot\osTicket\include" change file "ost-sampleconfig.php" to "ost-config.php"

![image](https://github.com/user-attachments/assets/30df95f0-5a08-439e-a77a-e5e674dd51e4)
<br />
<br />

65. Entry in the properties of the 'ost-config.php' file

![image](https://github.com/user-attachments/assets/e9b8d8ed-7ba4-42d3-a30c-1fbaefa98963)
<br />
<br />

66. Press 'Security' button

![image](https://github.com/user-attachments/assets/6bb70dbd-b33b-41ef-8983-b7eaab275716)
<br />
<br />

67. Click on 'Advanced' 

![image](https://github.com/user-attachments/assets/e5326507-d0cb-4de6-98b4-1b08e0713d68)
<br />
<br />

68. Remove all inherited permissions from this object

![image](https://github.com/user-attachments/assets/338b43e1-384c-43d0-a43f-84c5c641e19f)
<br />
<br />

69. Click the 'Add' button

![image](https://github.com/user-attachments/assets/d4c74822-910a-4af1-8df3-1e73c2a7eb14)
<br />
<br />

70. Click on "Select a principal"

![image](https://github.com/user-attachments/assets/7ecca136-08d8-404a-b357-d2fe049a6a5b)
<br />
<br />

71. Click here and type in 'Everyone

![image](https://github.com/user-attachments/assets/2d9e748f-4516-4141-bc3f-c4fbb07b9146)
<br />
<br />

72. Click on the 'Check names' button

![image](https://github.com/user-attachments/assets/c60b43ba-67be-46d9-a097-a5f7a505f13d)
<br />
<br />

73. Press 'OK'

![image](https://github.com/user-attachments/assets/99ab9534-0704-458a-b107-357a7f964558)
<br />
<br />

74. Click on 'Full control'

![image](https://github.com/user-attachments/assets/82de95d9-7957-4f7d-b658-864c6ced963a)
<br />
<br />

75. Click 'OK'

![image](https://github.com/user-attachments/assets/bee9854c-1bc1-4b64-b7ec-318ef39b8f6d)
<br />
<br />

76. Click the 'Apply' button

![image](https://github.com/user-attachments/assets/03e40777-dea1-4d4a-8e73-6608b725db3d)
<br />
<br />

77. Press 'OK'

![image](https://github.com/user-attachments/assets/b13ceb8e-9c30-4717-8c95-d1f8e6caf11e)
<br />
<br />

78. Click "OK"

![image](https://github.com/user-attachments/assets/2c95b155-a1b9-46ac-be24-eae753ce0492)
<br />
<br />

79. On the osTicket web page, click "Continue"

![image](https://github.com/user-attachments/assets/d955a6ff-39ce-4985-9a17-abd0d1cb80c1)
<br />
<br />

80. Fill in the 'Admin user' and 'System settings' fields

![image](https://github.com/user-attachments/assets/94b1174b-a7c4-4125-bb34-3a088465f5c9)
<br />
<br />

81. Before establishing the database, it is necessary to connect to it using HeidiSQL. Install HeidiSQL and retain the default settings.

![image](https://github.com/user-attachments/assets/aad5237b-4a85-4b81-a691-95e1e78c1b63)
<br />
<br />

82. In HeidiSQL, click on 'New

![image](https://github.com/user-attachments/assets/5f3cac62-4db6-42c5-9d83-cdbfc6388c67)
<br />
<br />

83. Type in your root password (the password from the mySQL setup)
 
![image](https://github.com/user-attachments/assets/07f5590c-3b75-45c2-97cf-224c3903f9e6)
<br />
<br />
 
84. Click the 'Open' button

![image](https://github.com/user-attachments/assets/86d4d8cf-2974-4972-a955-45ab8d857771)
<br />
<br />

85. Click on 'Database'

![image](https://github.com/user-attachments/assets/8d00af8f-3dc2-4595-b26d-128d0b43dbf2)
<br />
<br />

86. Type "osTicket" and click "OK"

![image](https://github.com/user-attachments/assets/14420103-3a1a-4c5b-bcbf-9ee38d380c54)
<br />
<br />

87. Fill in the "Database settings" field

![image](https://github.com/user-attachments/assets/90fee285-06c4-4cb4-b84a-49b7d0422227)
<br />
<br />

88. Click 'Install'

![image](https://github.com/user-attachments/assets/31d7b88f-11d8-444e-bcf8-65b1c6f46556)
<br />
<br />

<h2>Successfully Installed osTicket! What's Next?</h2>

<b>By following the steps outlined in this comprehensive guide, you have now successfully installed osTicket and have it ready to use! But the setup doesn't end here. osTicket is now installed and ready for use! In the next project, I will extend this foundation by providing a detailed walkthrough on configuring agents (including their permissions and access levels), managing users, and exploring other key configuration options to tailor osTicket to specific support workflows.

[Next: osTicket: Post-Installation Configuration](https://github.com/HeidiBolivar/post-install-config)
</b>
<br />
<br />
</p>
