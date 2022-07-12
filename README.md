<b>Project Two: TCP Sender/Receiver</b>

<b>Done by: Mohammed Arham (maj596) and Muhammad Areeb (maa1150)</b>

The program was written and compiled on Catalina Mac OS using GCC compiler. If you want to compile this on mac then please remove -lpthread from the makefile, if you want to run it on linux then keep the -lpthread command. <b></b>

<b>Instructions To Run the Program</b>

Download the zip file.

Use a terminal to change directory to the folder with all the files.

Run ‘make’ in terminal. Now a folder called 'obj' should be created in the root directory.

Now open another terminal and cd to the 'obj' folder and run the receiver.exe file first. The program requires you to run the receiver first and only then run the sender.exe file in seprate terminal window.

An example: in terminal one, you cd to the root folder, and type ./obj/rdt_reciever anyPortYouWant whateverNameYouGiveForReceivedFile.anyExtension

./rdt_receiver 9000 finalReceived.pdf

in terminal two, you would be in the obj folder, and type ./rdt_sender yourIPadress anyPortYouWant anyFileInObjFolder.anyExtension

./rdt_sender 10.225.123.132 9000 final.pdf

NOTE: the anyPortYouWant number should be the same

KNOWN BUGS AND LIMITATIONS: 

Sometimes when you make the transmission, the rdt_sender terminal would terminate correctly and the file would be transfeered but the rdt_receiver terminal would hang and not terminate. We think it also could be that we lose the end acknowledgement packet so the receiver doesnt know that the file was received completely and successfully (since it receives the correct file).

Sometimes when you make a transmission both the terminal would hang. However the frequency of this happening is very low and hard to replicate.

Both of these 2 bugs occured in instances where it was our first transmission of a new file or when we ran the program for the first time, but the frequency of it happening even in those cases were low, so it was hard to study. As such we can't pinpoint if it's a code issue, or maybe a state issue (network/OS/etc). However, repeated running of the program usually solves them. 

When there is no delay but loss, so like  mm-delay 0 mm-loss uplink 0.8 mm-loss downlink 0.5 our program hangs and we think its because our program cant keep up with retransmission but we are still not sure why it happens. But it performs fine when there is delay and loss. The program also works fine when there is just delay or just loss (when we were testing). We think since there is always delay in real world this is not a big deal.



