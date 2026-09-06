01. Port is in use
------------------------------
The log shows that Apache cannot start because Port 80 is already occupied by Process ID (PID) 4. On Windows systems, PID 4 refers directly to the system kernel (NT Kernel & System). This means an official Windows network service is already using the port. [1, 2, 3] 
You can resolve this issue quickly using either of the two methods below:
## Method 1: Change Apache's Default Port (Recommended)
This is the safest option because it avoids disabling important Windows services. You can configure Apache to run on an open port like 8080 instead. [4] 

   1. On the XAMPP Control Panel, look at the Apache row and click the Config button.
   2. Select Apache (httpd.conf) from the dropdown menu.
   3. In the notepad file that opens, press Ctrl + F and search for Listen 80.
   4. Change Listen 80 to Listen 8080.
   5. Find the line ServerName localhost:80 and change it to ServerName localhost:8080.
   6. Save (Ctrl + S) and close the file.
   7. Click Start next to Apache on your XAMPP Panel. [2, 5, 6, 7, 8] 

Note: After making this change, you will need to access your local projects by adding the port to the URL in your browser, like this: http://localhost:8080/your_project/. [2, 5] 
------------------------------
## Method 2: Stop the Conflicting Windows Service
If you want to keep using the default port 80, you have to disable the Windows system service hogging it. Usually, this is the World Wide Web Publishing Service (IIS). [2, 6, 9] 

   1. Press Win + R on your keyboard, type services.msc, and press Enter.
   2. Scroll down until you find World Wide Web Publishing Service.
   3. Right-click it and select Properties.
   4. Click the Stop button.
   5. Change the Startup type dropdown menu to Disabled so it doesn't turn back on when your computer restarts.
   6. Click Apply, then OK, and try starting Apache in XAMPP again. [2, 9, 10] 

Would you like help checking for other common apps that use this port (such as Skype or SQL Server Reporting Services) if these two fixes don't work? [2, 11] 

[1] [https://stackoverflow.com](https://stackoverflow.com/questions/23317372/xampp-port-80-in-use-by-unable-to-open-process-with-pid-4)
[2] [https://stackoverflow.com](https://stackoverflow.com/questions/20558410/xampp-port-80-in-use-by-unable-to-open-process-with-pid-4-12)
[3] [https://www.daniweb.com](https://www.daniweb.com/programming/web-development/threads/466302/apache-not-running-on-xampp-control-panel-v3-2-1)
[4] [https://www.youtube.com](https://www.youtube.com/watch?v=Yen-xjCuVqg)
[5] [https://www.youtube.com](https://www.youtube.com/watch?v=XFq18jHe58M&t=36)
[6] [https://www.w3docs.com](https://www.w3docs.com/snippets/php/xampp-port-80-in-use-by-unable-to-open-process-with-pid-4)
[7] [https://www.youtube.com](https://www.youtube.com/watch?v=QaIMoc4MOtg)
[8] [https://www.youtube.com](https://www.youtube.com/watch?v=fllIrG9D88I)
[9] [https://help.hosturly.com](https://help.hosturly.com/vps-hosting/mWBYBHFGnkz2zW7GQC7kRK/xampp-error-port-80-in-use/1pgwcJSEf7rYRxg4Si1JZ6)
[10] [https://rajivverma.me](https://rajivverma.me/blog/tech/how-tos/xampp-port-80-blocked-pid-4-windows-10/)
[11] [https://stackoverflow.com](https://stackoverflow.com/questions/23317372/xampp-port-80-in-use-by-unable-to-open-process-with-pid-4)
