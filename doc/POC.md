Instruction to get access to AgroCD interface.
1.	Open/Create GitHub Codespace for repo https://github.com/svolkov/startup
2.	Install k3d:
 curl -s https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh | bash
3.	Create cluster:
 k3d cluster create agro-cd-cluster
4.	Install Agro CD:
  kubectl create namespace argocd
 kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
5.	Download Argo CD CLI:
 curl -sSL -o argocd-linux-amd64 https://github.com/argoproj/argo-  cd/releases/latest/download/argocd-linux-amd64
 sudo install -m 555 argocd-linux-amd64 /usr/local/bin/argocd
 rm argocd-linux-amd64
6.	Setup access to Argo CD server:
 kubectl port-forward svc/argocd-server -n argocd 8080:443
 (in the Codespace’s tab ‘Ports’ set ‘https’ and ‘Public’ for port 8080)
7.	Open localhost:8080 in the browser – Login page should be displayed.
![Screenshot_argo_cd_login](https://github.com/svolkov/startup/assets/9334152/3a58ae0f-94fc-4580-ac36-4e4b8b49055a)


8.	Get admin password via Argo CD CLI:
 argocd admin initial-password -n argocd
9.	Login - Argo CD interface should be displayed
![Screenshot_argo_interface](https://github.com/svolkov/startup/assets/9334152/bc726aee-9717-44a4-ac45-b9afe1d7690c)

