```bash
   #!/bin/sh

   #Select the rout directory.
   $cd ~

   #Create a file where both ip and subnet mask will be saved.
   $touch ip_mask.txt

   #Send the relevant infomation to a new file.
   $ifconfig >> ifconfig.txt

   #Look for the information we want and change the name.
   $sed -n '2p' ifconfig.txt > ip_mask.txt
   $sed -i 's/inet/ipv4/g' ip_mask.txt
   $awk '{print $1,$2,$3,$4}' ip_mask.txt > ip_maskn.txt

   #Output the ipv4 and subnet mask in the cli. 
   $cat ip_maskn.txt

   #We have our code. Just remove the files created in our root.

   $rm ifconfig.txt ip_mask.txt ip_maskn.txt   
    
```

