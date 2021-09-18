# CKS-PREP
Repository for CKS Practice and Docs


gcloud auth login
gcloud projects list
gcloud config set project YOUR-PROJECT-ID

gcloud services enable container.googleapis.com storage.googleapis.com anthos.googleapis.com anthosgke.googleapis.com cloud.googleapis.com cloudresourcemanager.googleapis.com containerregistry.googleapis.com file.googleapis.com ; gcloud services list --enabled



# cks-master


gcloud compute instances create cks-master --zone=us-west1-a --machine-type=e2-medium --image=ubuntu-1804-bionic-v20201014 --image-project=ubuntu-os-cloud --boot-disk-size=50GB


sudo -i
bash <(curl -s https://raw.githubusercontent.com/killer-sh/cks-course-environment/master/cluster-setup/latest/install_master.sh)


# cks-worker

gcloud compute instances create cks-worker --zone=us-west1-a --machine-type=e2-medium --image=ubuntu-1804-bionic-v20201014 --image-project=ubuntu-os-cloud --boot-disk-size=50GB


sudo -i
bash <(curl -s https://raw.githubusercontent.com/killer-sh/cks-course-environment/master/cluster-setup/latest/install_worker.sh)


# run the printed kubeadm-join-command from the master on the worker

gcloud compute firewall-rules create nodeports --allow tcp:30000-40000
