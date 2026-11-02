<p align="center"><img width="399" height="201" alt="image" src="https://github.com/user-attachments/assets/c12a30e5-6391-45a4-a7e0-ea2617631921" /></p>


K9s is an open-source, terminal-based UI designed to help you interact with your Kubernetes clusters. It provides a real-time view of all your resources—pods, deployments, services, CRDs, and more—right from your terminal. K9s simplifies cluster management by offering quick keyboard shortcuts and intuitive navigation, allowing you to troubleshoot and operate clusters faster than with `kubectl` alone.

### Automatic Installation Via Webi (Recommended) 

- **For Linux and macOS:**

    ```sh
    curl --http1.1 -fL \
        https://github.com/derailed/k9s/releases/download/v0.51.0/k9s_Linux_amd64.tar.gz \
        -o ~/Downloads/k9s_Linux_amd64.tar.gz
    ```

- **Extract manually**

  ```sh
  cd ~/Downloads
  tar -xzf k9s_Linux_amd64.tar.gz
  ```

- **Install K9s manually**

  ```sh
  sudo install k9s /usr/local/bin/k9s
  ```

- **Check & Verify**

  ```sh
  k9s version
  ```


### Common Keyboard Shortcuts

| Key / Command | Function |
| :--- | :--- |
| **Arrow Keys (Up/Down/Left/Right)** | Navigate lists and views. |
| **Enter** | View details of a selected resource (e.g., list deployment's pod, list pod's container). |
| **Esc** | Go back to the previous view. |
| **/** | Search resources (e.g., `/nginx`). |
| **:** | Switch resource views (e.g., `:pod`, `:deploy`, `:service`). |
| **e** | Edit selected resource manifest. |
| **d** | Describe selected resource. |
| **Ctrl+d** | Delete selected resource. |
| **l** | View logs of a pod. |
| **s** | Shell into the selected pod. |
| **y** | Show YAML manifest. |
| **0** | Switch to all namespace view. |
| **?** | Show help. |
| **Ctrl+c** | Quit the application. |


##  Resource navigation cheat sheet

| Command | Kubernetes Resource |
|---|---|
| `:po` | Pods |
| `:deploy` or `:dp` | Deployments |
| `:rs` | ReplicaSets |
| `:sts` | StatefulSets |
| `:ds` | DaemonSets |
| `:svc` | Services |
| `:ing` | Ingress |
| `:ns` | Namespaces |
| `:pv` | PersistentVolumes |
| `:pvc` | PersistentVolumeClaims |
| `:sc` | StorageClasses |
| `:cm` | ConfigMaps |
| `:secret` | Secrets |
| `:job` | Jobs |
| `:cj` | CronJobs |
| `:node` | Nodes |
| `:sa` | ServiceAccounts |
| `:cr` | ClusterRoles |
| `:crb` | ClusterRoleBindings |
