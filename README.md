# Creating-a-Persistent-Disk
Creating a Persistent Disk Google cloud Arcade


Task - 1
gcloud auth list gcloud config list project
gcloud compute instances create gcelab --zone us-centrall-c


Task - 2
gcloud compute disks create mydisk --size=200GB
--zone Us-central1-c


Task - 3
gcloud compute instances attach-disk gcelab --disk mydisk --zone us-central1-c 
ls -1 /dev/disk/by-id/
