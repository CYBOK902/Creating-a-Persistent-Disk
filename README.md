# Creating-a-Persistent-Disk
Creating a Persistent Disk Google cloud Arcade

Task - 1 
gcloud auth list
gcloud config list project
gcloud compute instances create gcelab --zone us-central1-c

Task - 2
gcloud compute disks create mydisk --size=200GB \
--zone us-central1-c

Task - 3
gcloud compute instances attach-disk gcelab --disk mydisk --zone us-central1-c
ls -l /dev/disk/by-id/

gcloud compute instances attach-disk gcelab --disk mydisk --zone us-central1-c

gcloud compute ssh gcelab --zone us-central1-c

ls -l /dev/disk/by-id/
sudo mkdir /mnt/mydisk

sudo mkfs.ext4 -F -E lazy_itable_init=0,lazy_journal_init=0,discard /dev/disk/by-id/scsi-0Google_PersistentDisk_persistent-disk-1

sudo mount -o discard,defaults /dev/disk/by-id/scsi-0Google_PersistentDisk_persistent-disk-1 /mnt/mydisk

sudo nano /etc/fstab
/dev/disk/by-id/scsi-0Google_PersistentDisk_persistent-disk-1 /mnt/mydisk ext4 defaults 1 1
