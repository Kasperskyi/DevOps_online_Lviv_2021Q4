# Task 7.1

## Part A

```
#!/bin/bash


#This function displays description of tool
function description
{
	echo -e "Description \n"
	echo -e "	netscan - network exploration tool and port scanner \n"
	echo -e "Available keys for netscan: \n"
	echo "	--all		displays the IP addresses and symbolic names of all hosts in subnet"
	echo -e "			(example: ./netscan --all 192.168.1.0/24)\n"
	echo "	--target	displays a list of open system TCP ports"
	echo "			(example: ./netscan --target)"
}

#This function shows existed ip adresses and names of hosts in subnet 
function ipscan
{
	#Check existing  nmap tool
	test -e /usr/bin/nmap
	if [ "$?" == "0" ]
	then 
		echo "Starting scan network ..."
	else 
		echo "Please wait for preparing component ..."
		sudo apt install nmap -y
	fi

#Scanning network
	addr=$1
	echo "Next hosts are in network:  "
	nmap -sP $addr | awk 'NR % 2 == 0 {print "Hostname:" $5 "    " "IP address:" $6}' | sed 's/(//g; s/)//g'
}

#This function checking listen TCP port  
function portscan
{
	echo "Next TCP ports are open:"
	ss -atlpn  
}

#General function 
if [ "$#" == "0" ]
	then description

elif [ "$1" == "--all" ]
	then ipscan $2

elif [ "$1" == "--target" ]
	then portscan 

fi
```

**Results:**

![image](https://user-images.githubusercontent.com/42848618/147923917-edd05a54-43d2-4d4f-90a1-1b7053f3cfed.png)


## Part B
```
#!/bin/bash

#Variables
logfile=$2

#This function displays description of tool
function error
{
	echo -e "Invalid value. You can find existed keys using --help"
}

function description
{
	echo -e "\nDescription \n"
	echo -e "	loganalyzer - tool for analyze logs \n"
	echo -e "Available keys for loganalyzer: \n"
	echo -e "	--help		displays the description of tool and provide list of keys\n"
	echo -e "	--mri		displays the most requested ips\n"
	echo -e "	--mrp		displays the most request pages\n"
	echo -e "	--nrfi		displays number of requests from each ips\n"
	echo -e "	--nep		displays non-existent pages\n"
	echo -e "	--tmrs		displays time of most requested sites\n"
	echo -e "	--bats		displays bots which accessed to site\n"
	echo -e "	(example: ./logscanner.sh --nep file_name number_line)"
}

#1.This function shows the most requested ips 
function mri
{
	echo: "The most requested ip are:"
	cat $logfile | grep -oE "([0-9]{1,3}\.){3}[0-9]{1,3}" | sort | uniq -c | sort -gr | head -n $2
}

#2. This function shows the most requested pages  
function mrp
{
	echo "The most requested pages are:"
	cat $logfile | awk '{print $7}' | sort | uniq -c | sort -gr | head -n $2 
}

#3.This function shows number of requests from each ips 
function nrfi
{
        echo "See below a list of requestS:" 
        cat $logfile | grep -oE "([0-9]{1,3}\.){3}[0-9]{1,3}" | sort | uniq -c | sort -gr | awk '{print "There is " $1 " requests from IP: " $2}' | head -n $2
}

#4. This function shows non-existent pages 
function nep
{
	echo "See beloow list of non-existent pages:"
	cat $logfile | grep -w '404' | awk '{ print $7 }' | sort | uniq | head -n $2 
}

#5. This function shows time of most requested sites
function tmrs
{
      	echo "See beloow time of most requested sites:"
        cat $logfile | awk '{ print "requsts got in " $4 "]" }' | sort | uniq -c | sort -gr | head -n $2 
}

#6. This function shows bots which accessed to site
function bats 
{
        echo "See beloow list of bots:"
        grep "bot" $logfile | awk -F\" '{ print $6 }' | sort | uniq -c | head -n $2 
}

#General function 
if [ "$#" == "0" ]
      	then error

elif [[ -z "$1" ]]
      	then echo "Error. Please find existed keys and example using --help"

elif [ "$1" == "--help" ]
      	then description

elif [[ -z "$2" ]]
      	then echo "Error. Please find existed keys and example using --help"

elif [ "$1" == "--mri" ]
      	then mri $2 $3

elif [ "$1" == "--mrp" ]
        then mrp $2 $3 

elif [ "$1" == "--nrfi" ]
      	then nrfi $2 $3 

elif [ "$1" == "--nep" ]
        then nep $2 $3 

elif [ "$1" == "--tmrs" ]
        then tmrs $2 $3 

elif [ "$1" == "--bats" ]
        then bats $2 $3 
fi
```
**Results:**

![image](https://user-images.githubusercontent.com/42848618/147926863-e7dea81d-9fca-4b76-a563-4d0f5af468a5.png)

![image](https://user-images.githubusercontent.com/42848618/147926978-bfe2cbc3-40bc-4a07-b2ba-b95339c9b76c.png)



## Part C
```
#!/bin/bash

#General function 
if [ "$#" == "0" ]
	then echo -e "Please specify source directory and destination directory"
	exit 0

elif ! [[ -d "$1" ]]
	then echo -e "Source directory is not exist"
	exit 0

elif [[ -z "$2" ]]
	then echo -e "Please specify source destination directory"
	exit 0

elif ! [[ -d "$2" ]]
	then echo -e "Destination directory is not exist. Creating directory..."
	mkdir $2
	echo -e "$2 created"
fi

#Variables
srdir=$1
dsdir=$2
temp=/tmp/
log=/var/log/backup_script.log
tstamp=$(date +'%d.%m.%Y-%H:%M:%S')
usr=$(whoami)

sudo touch $log
sudo chmod 644 $log
sudo chown $usr:$usr $log

ls $srdir > $temp/srls.txt
ls $dsdir > $temp/dsls.txt

#Copy files
for var1 in $(diff -y --suppress-common-lines $temp/srls.txt $temp/dsls.txt | awk '{ print $1 }' | sed 's/<//g; /^[[:space:]]*$/d')
do 
	cp -r $srdir/$var1  $dsdir 
	echo "$tstamp Copied $var1" >> $log
	echo "$var1 is being copied over to $dsdir"
done

#Update files
for var2 in $(find $srdir -printf "%P\n") ; do
    if [ -a $dsdir/$var2 ] ; then
        if [ $srdir/$var2 -nt $dsdir/$var2 ] ; then 
        cp -r $srdir/$var2 $dsdir/$var2
        echo "$tstamp Updated $var2" >> $log
        echo "Newer version of $var2 detected, copied"
        fi
    fi
done

#Delete files
for var3 in $(diff -y --suppress-common-lines $temp/srls.txt $temp/dsls.txt | awk '{ print $2 $3 }' | sed 's/<//g; s/|//g; /^[[:space:]]*$/d')
do 
      rm -rf $dsdir/$var3
      echo "$tstamp Deleted $var3" >> $log
      echo "$var3 is being deleted from $dsdir"
done
```
**Results:**

![image](https://user-images.githubusercontent.com/42848618/147929603-b9b03421-0882-4e60-9340-5231cc8b97fc.png)

![image](https://user-images.githubusercontent.com/42848618/147933412-acee03fa-8fa4-435b-8860-b866212b22f6.png)
