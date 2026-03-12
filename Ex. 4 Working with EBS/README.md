# Lab 4 – Working with Amazon Elastic Block Store (EBS)

## Author

* **Name**: Bala janani.S
* **Register Number**: 212223060027
* **Date of Submission**: 12/03/2026

---

## Objective

The objective of this experiment is to understand how Amazon Elastic Block Store (EBS) provides persistent block-level storage for EC2 instances. This lab focuses on creating and attaching an EBS volume, formatting and mounting it on an EC2 instance, storing data, and verifying data persistence after instance reboot.

---

## Prerequisites

* Basic understanding of cloud computing concepts
* AWS account or AWS Academy Lab access
* An existing EC2 instance (Amazon Linux 2 preferred)
* Basic knowledge of Linux commands

---

## Tools Used

* AWS Management Console
* Amazon EC2
* Amazon EBS
* SSH Client (Terminal / PuTTY)

---

## Tasks Performed

### Task 1: Explore Amazon EBS

Explore the Amazon EBS service through the EC2 dashboard. Observe different volume types such as General Purpose SSD (gp2/gp3), Provisioned IOPS SSD, Throughput Optimized HDD, and Cold HDD.

---

### Task 2: Create an EBS Volume

Create a new EBS volume in the same Availability Zone as the EC2 instance. Choose an appropriate size and volume type.

---

### Task 3: Attach EBS Volume to EC2 Instance

Attach the created EBS volume to the running EC2 instance as an additional block device.

---

### Task 4: Format the EBS Volume

Connect to the EC2 instance using SSH and format the attached volume with a file system (for example, ext4).

---

### Task 5: Mount the EBS Volume

Mount the formatted volume to a directory in the EC2 instance (for example, /data or /mnt/ebs).

---

### Task 6: Store Data in EBS Volume

Create files and directories inside the mounted EBS volume and store sample data.

---

### Task 7: Verify Data Persistence

Reboot the EC2 instance and verify that the data stored in the EBS volume is still available after reboot.

---

## Workflow (Student Explanation)

(Write the steps you followed in your own words)

First, I logged in to the AWS Management Console.

I navigated to the EC2 Dashboard.

I explored the Elastic Block Store (EBS) section under EC2.

I observed different volume types such as General Purpose SSD (gp2/gp3), Provisioned IOPS SSD, Throughput Optimized HDD, and Cold HDD.

I clicked on “Volumes” and selected “Create Volume.”

I chose the required volume type (General Purpose SSD – gp3).

I entered the desired storage size (for example, 8 GB).

I selected the same Availability Zone as my running EC2 instance.

I clicked on “Create Volume” to create the EBS volume.

After the volume was created, I selected the volume and clicked on “Attach Volume.”

I selected my running EC2 instance and attached the volume as a new device (for example, /dev/xvdf).

I connected to my EC2 instance using SSH from the terminal.

I checked the attached disk using the command lsblk to verify the new volume.

I formatted the attached volume using the command: sudo mkfs -t ext4 /dev/xvdf

I created a directory to mount the volume using: sudo mkdir /mnt/ebs

I mounted the volume to the directory using: sudo mount /dev/xvdf /mnt/ebs

I verified that the volume was mounted successfully using the df -h command.

I created sample files inside the mounted directory using: sudo touch /mnt/ebs/sample.txt

I stored some sample data inside the file.

I rebooted the EC2 instance from the AWS Console.

After rebooting, I reconnected to the instance using SSH.

I checked the mounted directory and verified that the stored data was still available.

This confirmed that the EBS volume provides persistent storage even after instance reboot.



---

## Output Screenshots (Attach 3)

### Screenshot 1: EBS Volume Created

<img width="1920" height="1020" alt="Screenshot 2026-02-27 113140" src="https://github.com/user-attachments/assets/abe08211-9e03-442d-8cf6-11f256491fd8" />

---

### Screenshot 2: EBS Volume Attached to EC2

<img width="1920" height="1020" alt="Screenshot 2026-02-27 113407" src="https://github.com/user-attachments/assets/0cce76a9-2699-45d4-96fb-730386419082" />
<img width="1216" height="1020" alt="Screenshot 2026-02-27 113518" src="https://github.com/user-attachments/assets/b8109f11-8c55-4eee-852e-7dd75fc73772" />
<img width="1216" height="1020" alt="Screenshot 2026-02-27 114503" src="https://github.com/user-attachments/assets/ac501e0f-b03c-4a28-ba76-d4a5613f2577" />

---

### Screenshot 3: Mounted Volume with Data

<img width="1216" height="1020" alt="Screenshot 2026-02-27 114711" src="https://github.com/user-attachments/assets/4ddbb3a8-7b07-48d9-88c0-b89ff374707a" />
<img width="1216" height="1020" alt="Screenshot 2026-02-27 115253" src="https://github.com/user-attachments/assets/efd98e70-1a71-4e9b-a6ac-fd7f115a7730" />


---

## Result / Conclusion
This experiment demonstrated how Amazon EBS provides persistent storage for EC2 instances. By creating, attaching, formatting, and mounting an EBS volume, and by verifying data after reboot, the concept of durable block storage in the cloud was clearly understood.


