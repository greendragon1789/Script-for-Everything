When using Gcloud with multi environment, we need transfer betweens environments. We need script to faster run. Edit in the .zshrc or .bashrc and run it after login.
```
# Based on the shell we are using, we will modify either ~/.bashrc or ~/.zshrc file.
# If you don’t have idea about this, just go for the ~/.bashrc file.
# Change environment gcloud in Be
function swe() {
        case $1 in
                dev )   gcloud config set project gam-project-cgd-x0l-zm4
                        gcloud container clusters get-credentials bu1-k8s-dev --zone=asia-southeast1-a
                        ;;
                stage ) gcloud config set project veep-staging
                        gcloud container clusters get-credentials default --zone=asia-southeast1-a
                        ;;
                prod )  gcloud config set project veep-production
                        gcloud container clusters get-credentials default --zone=asia-southeast1-a
                        ;;
                devops ) gcloud config set project veep-devops-practice
                         gcloud container clusters get-credentials demo-k8s --zone=asia-southeast1-a

                         ;;
                azui )  gcloud config set project project-azui
                        ;;
                loyalty )       gcloud config set project veep-loyalty
                                ;;
                * ) echo "CLGT"
        esac
}
```
