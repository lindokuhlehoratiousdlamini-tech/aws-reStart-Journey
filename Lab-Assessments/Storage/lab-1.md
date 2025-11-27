# Working with Amazon EBS

## Lab overview
In this lab, I learn to create an EBS volume, attach it to an EC2 instance, set up a file system on it, and make a snapshot backup.
## Objectives
By the end of this lab, you will be able to do the following:
- Create an EBS volume.
- Attach and mount an EBS volume to an EC2 instance.
- Create a snapshot of an EBS volume.
- Create an EBS volume from a snapshot.
## Challange 


## Task 1: Creating a new EBS volume
I open EC2, check the Lab instance’s Availability Zone, then go to Volumes to see the existing 8 GiB EBS volume attached to it.

Choose Create volume, and configure the following options:
- Volume type: Choose General Purpose SSD (gp2).
- Size (GiB): Enter 1. 
- Note: You might be restricted from creating large volumes.
- Availability Zone: Choose the same Availability Zone as your EC2 instance (which is us-west-2a in this case).

Choose Create volume, and configure the following options:
- Volume type: Choose General Purpose SSD (gp2).
- Size (GiB): Enter 1. 
- Note: You might be restricted from creating large volumes.
- Availability Zone: Choose the same Availability Zone as your EC2 instance (which is us-west-2a in this case).

## Task 2: Attaching the volume to an EC2 instance
You now attach your new volume to an EC2 instance.

Select My Volume.

From the Actions menu, choose Attach volume.

From the Instance dropdown list, choose the Lab instance.

For the Device name field select /dev/sdb. Commands that you run later in this lab include this device identifier. 

Choose Attach volume.

The Volume state of your new volume is now In-use.

## Task 3: Connecting to the Lab EC2 instance
On the AWS Management Console, in the Search bar, enter and choose EC2 to open the EC2 Management Console.

In the navigation pane, choose Instances.

From the list of instances, select the Lab instance.

Choose Connect.

On the EC2 Instance Connect tab, choose Connect.

## Task 4: Creating and configuring the file system
To view the storage that is available on your instance, in the EC2 Instance Connect terminal, run the following command:
________________________________________________
df -h
___________________________________________________

You should see output similar to the following:

To create an ext3 file system on the new volume, run the following command:
_________________________________________________________
sudo mkfs -t ext3 /dev/sdb
_____________________________________________________________
To create a directory to mount the new storage volume, run the following command:
______________________________________________________
sudo mkdir /mnt/data-store
______________________________________________________
To mount the new volume, run the following command:
______________________________________________________
sudo mount /dev/sdb /mnt/data-store
echo "/dev/sdb   /mnt/data-store ext3 defaults,noatime 1 2" | sudo tee -a /etc/fstab
__________________________________________________________
To view the configuration file to see the setting on the last line, run the following command:
_________________________________________________________________
cat /etc/fstab
_______________________________________________________________
To view the available storage again, run the following command:
_______________________________________________________________
df -h
_________________________________________________________________
The output now contains an additional line similar to the following: /dev/nvme1n1


To create a file and add some text on the mounted volume, run the following command:
____________________________________________________________________
sudo sh -c "echo some text has been written > /mnt/data-store/file.txt"
__________________________________________________________________
To verify that the text has been written to your volume, run the following command:
______________________________________________________________________
cat /mnt/data-store/file.txt
_________________________________________________________________________

## Task 5: Creating an Amazon EBS snapshot
On the EC2 Management Console, choose Volumes, and select My Volume.

From the Actions menu, choose Create snapshot.

In the Tags section, choose Add tag, and then configure the following options:
- Key: Enter Name.
- Value: Enter My Snapshot.-
- Choose Create snapshot.

In your EC2 Instance Connect terminal window, to delete the file that you created on your volume, run the following command:
________________________________________________________________________
sudo rm /mnt/data-store/file.txt
_________________________________________________________________________

To verify that the file has been deleted, run the following command:
__________________________________________________________________
ls /mnt/data-store/file.txt
_______________________________________________________________

# Task 6: Restoring the Amazon EBS snapshot

           Task 6.1: Creating a volume by using the snapshot

On the EC2 Management Console, select My Snapshot.

From the Actions menu, choose Create volume from snapshot.

For Availability Zone, choose the same Availability Zone that you used earlier.

In the Tags - optional section, choose Add tag, and then configure the following options:
- Key: Enter Name.
- Value: Enter Restored Volume.
- Choose Create volume.
- To see your new volume, in the left navigation, choose Volumes.
- The Volume status of your new volume is Available.
            Task 6.2: Attaching the restored volume to the EC2 instance

Select Restored Volume.

From the Actions menu, choose Attach volume.

From the Instance dropdown list, choose the Lab instance.

For the Device name field, choose /dev/sdc. You use this device identifier in a later task.

Choose Attach volume.

The Volume status of your volume is now In-use

            Task 6.3: Mounting the restored volume
To create a directory for mounting the new storage volume, in the EC2 Instance Connect terminal, run the following command:
__________________________________________________
sudo mkdir /mnt/data-store2
___________________________________________________
To mount the new volume, run the following command:
____________________________________________________
sudo mount /dev/sdc /mnt/data-store2
_____________________________________________________
To verify that the volume that you mounted has the file that you created earlier, run the following command:
______________________________________________________
ls /mnt/data-store2/file.txt
_______________________________________________________
