# udp-flood
This is a UDP packet flooding script i created for my Science Fair at school. This script is to be used for educational purposes ONLY! DoS attacks are illegal, and i am in no way responsible for any damages or misuse of this script. Only use this script on yourself, or with the written consent of a server or network owner, for education reasons. This script is dangerous, and will flood your server with UDP packets. Use at your own risk!

<img src="https://cdn.discordapp.com/attachments/572508218673332244/653803618960408627/unknown.png">

<h2>Experiment Overview</h2>


<h3>Problem</h3>
How do requests affect a servers incoming latency?

<h3>Hypothesis</h3>
	
If I send many UDP packets to a server for 60 seconds, then the server’s incoming latency will increase because the server cannot handle many requests at one time.

<h3>Materials</h3>
	You will need: A Windows 10 computer to send packets from (Localhost), A Ubuntu 18.04 server from DigitalOcean.com with 2 vCPUs and 4gb RAM, Xampp software 
  
<h3>Procedure</h3>

1. First, you will need a hosting server. To get accurate data, you should use a Ubuntu 18.04.04 Virtual Private Server (VPS) with 2vCPU(s), 25GB SSD, 4GB ram, 4TB transfer x64 from DigitalOcean.com. You can use any server, however the network and CPU differences may cause a difference in results.

2. After you purchase a droplet (VPS) from DigitalOcean, Follow all prompts by DigitalOcean to continue setting up you hosting server, and getting the root password. Once finished the setup process, you may login. On a different Windows Computer, press Windows Key + R at the same time. Then, in the prompt, type “CMD”. Your Command Prompt will open. Type the following command: “ssh root@IP”. Fill in “IP” with the IPv4 provided on the DigitalOcean website. Then press enter. NNow, it will prompt for your password. Type or paste (To paste, right click) your root password provided by DigitalOcean during the setup process. NOTE: You will not be able to see the password as you type it, the  After, it will ask you to save this host to your computer. Type “yes” and press enter. If you logged in correctly, you will see something such as “Root@Name:#~”. If you have any issues logging in, setting up, or receiving your root password, contact DigitalOcean.

3. Third you will set up the UDP flooding script. First, you will have to download a tool to run the script. Go to https://www.apachefriends.org/download.html and download the Xampp tool. Find your system requirements, and click download. When the .exe file is finished downloading, you will need to run the file. Once the program starts, click “Next”. On the next screen, select all of the check boxes, and click “Next”. Finally, follow the prompts by clicking “Next” until the green status bar appears. During this process, you may get some pop up prompts. Click “Allow Access” on any that occur. If another command prompt opens, ignore it. This is just a part of the download process. After the status bar reaches the end, the download is complete, and you can click “Finish”. Select the American Flag for English, and click “Save”. Then, you will have two prompts. On the “Configuration of Control Panel” prompt, select “Save”. On the other prompt (“XAMPP Control Panel”), select “Start” next to “Apache”,  and “MySQL”. You may receive another prompt, if so select “Allow Access”. Now, click Windows Key + R once again. This time in the prompt, type “explorer”. Once the menu opens, you will have to scroll on the left sidebar until you find “This PC”. Once you find “This PC”, you can click on it. Then flind “Windows (C:)” in the right side of the menu. Once found, double click it. It will open up a list of folders. You will need to search for the folder called “xampp” and double click it. Then, find the folder “htdocs” and double click the folder. Now, you will see a few files. You should see a file called “index” or “index.php”. Right click this file, and press “Delete”. Now, you will need to install the UDP script. Inside of the File Explorer menu, click Shift + Right Click. Then press “Open PowerShell window here”. (This may say “Open Command Prompt window here”) Then type “git clone https://github.com/C0braD3v/udp-flood”. Once the file is finished installing, and you see “done.”, you may close the PowerShell or Command Prompt window that you ran the command in. Back in file explorer, you will see a new folder called “udp-flood”. Double click this folder. Then, you will see a file named “index” or “index.php”. Click and hold on this file, and drag your mouse to the top bar where it says “htdocs >”. Drop the file (unclick your mouse) on top of “htdocs” to move it into that folder. Then, click on “htdocs”. You should see the “index” or “index.php” file again. If you do, it means you have done this step correctly. Otherwise, you should retry this step. 

4. Now it is time to start runnning the trials. Go into your browser of choice, and in the URL bar type “http://127.0.0.1/”. It should open a page with green text reading “UDP PACKET FLOOD”. If it does not, then try step 3 again. If it does, then you may begin your first trial. In the “SERVER_IP” box, type the IPv4 provided earlier by DigitalOcean. In the “SECONDS” box, type “60”. Now, you should run your control test. Go back to the COmmand Prompt window from Step 2. Type the command “apt install nload”. Once you see something like “root@Name#~” then it is completed. Then, run the command “nload”. You should see “incoming” and “Outgoing” titles. You may begin your control test. Set a timer for 60 seconds, and once competed log the values in the “Cur” (current), “Avg” (average), and “Max” (maximum) sections under “Incoming”. This data will act as your control. Press Ctrl + C to exit. To start your first trial, you will go back to your browser, and click on the “SEND_PACKETS” button. (WARNING: UDP Flooding is a DoS attack. Ensure that the IP address listed in the “IP” textbox is the IP address of  a server you own, and or have written consent of the owner to run that test. DoS is  very dangerous and this procedure and script should be used for educational and scientific reasons only.) Very quickly go back to your Command Prompt window, and again type “nload”. Once completed, start a timer for 60 seconds. After the timer is complete, log the values in the “Cur” (current), “Avg” (average), and “Max” (maximum) sections under “Incoming”. Then press Ctrl + C. You will want to wait about five minutes before starting your next trial, as some packets may be delayed. To start your next trial, repeat the steps for trial one, and again for trial three.

5. experiment, you may go back to the “XAMPP Control PAnel” window. Click “Stop” on “Apache” and “MySQL”. You may then close this window, and uninstall XAMPP if you chose. Also, you may remove your DigitalOcean droplet on the DigitalOcean website by selecting “Kill Droplet”. 

<h3>Data</h3>
<img src="https://cdn.discordapp.com/attachments/590436031426199583/673315646460919837/unknown.png">

<h3>Conclusion</h3>
Overall, I believe this experiment went very well. When I sent many UDP packets to a server for 60 seconds, the servers incoming latency increased because the server cannot handle many requests at once. The data i collected during this experiment reflected my hypothesis, as the maximum and average packets increased from the control in each test. I noticed that in general, the UDP packets caused the server’s latency to increase, and cause processes to take longer to complete. The latency increased in spikes, and did not have one increase and decrease. I noticed that when the script began, the latency would shoot up, but then decrease, and increase becoming a “wave”, or spike in latency.  I found this very interesting as I expected the latency to peak as the packets came in, and not decrease until the packets were all processed. Possible errors in this experiment could have been starting or closing NLoad too late, causing the average latency to be slightly lower than accurate due to the average calculating after the packets were finished sending. To improve this, I could have used another computer to run the script in the browser, and a second one to view NLoad to ensure that it is stopped on time and the data is accurate. I could also try more trials, and longer periods of time for the packets. All in all, I learned very valuable information about UDP packets and DOS attacks.

<h3>Applications</h3>
I found that these attacks can lead to very high server latency, which can cause damage. If these attacks were used on large companies, they could lead to harming actual users on a server. For example, if someone were to use this flood on a company's server where they run a website, and a customer attempts to go on the site, they may not be able to as the server is busy handling requests of the packets. This could cause loss of traffic, revenue, and business for those running important processes on a server. This makes my experiment very valuable, to show the negative effects of these attacks, and how companies should take action to secure their servers to prevent this type of thing from happening on a real-world large scale.
