##New-network helm chart


## Parameters

### Quorum node deployment parameters

| Name                        | Description                                       | Value      |
| --------------------------- | ------------------------------------------------- | ---------- |
| `deployment.quorum_node_no` | The number of the deployed Quorum node            | `0`        |
| `deployment.company`        | The name of the company that makes the deployment | `RMS`      |
| `deployment.network_name`   | The name of the use case that is being deployed   | `ePI`      |
| `deployment.enode_ip`       | The Quorum node public ip address                 | `17.5.7.8` |
| `deployment.enode_ip_port`  | The Port of the Quorum node public address        | `30303`    |


### Helm post-install automated upload procedure to the use case shared repository. The configuration is made for git

| Name                                    | Description                                                                                                         | Value                                |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| `git_upload.enabled`                    | Enable the automatic upload to the use case shared repository of the shareable data                                 | `true`                               |
| `git_upload.email`                      | The email used by the git in order to upload the data                                                               | `""`                                 |
| `git_upload.user`                       | The user used by the git in order to upload the data                                                                | `""`                                 |
| `git_upload.git_repo_with_access_token` | The repository url eg. https://GITHUB-TOKEN:x-oauth-basic@github.com/PharmaLedger-IMI/helm-charts.git               | `""`                                 |
| `git_upload.git_repo_clone_directory`   | The folder name where the repository will be cloned when the upload procedure is initiated in the post-install step | `helm-charts`                        |
| `git_upload.git_repo_storage_path`      | The repository base folder name where the shareable data to will be uploaded                                        | `networks`                           |
| `git_upload.genesis_file_name`          | The name of the file that contains the genesis file                                                                 | `genesis.json`                       |
| `git_upload.validator_file_name`        | The name of the file that contains the validator address                                                            | `validator.address`                  |
| `git_upload.enode_file_name`            | The name of the file that contains the enode                                                                        | `enode`                              |
| `git_upload.enode_ip_file_name`         | The name of the file that contains the Quorum Node real ip address or dns                                           | `enode.ip`                           |
| `git_upload.enode_ip_port_file_name`    | The name of the file that contains the Quorum Node port                                                             | `enode.ip.port`                      |
| `git_upload.git_commit_description`     | The description associated with the commit into the use case shared repository of the shareable data                | `added genesis and node information` |


### Quorum docker image repository

| Name                     | Description                  | Value               |
| ------------------------ | ---------------------------- | ------------------- |
| `quorum_source.registry` | Quorum docker image registry | `quorumengineering` |
| `quorum_source.image`    | Quorum docker image name     | `quorum`            |
| `quorum_source.version`  | Quorum docker image version  | `21.7.1`            |


### Quorum node configurations

| Name                    | Description              | Value |
| ----------------------- | ------------------------ | ----- |
| `blockhain.blockperiod` | Quorum node block period | `3`   |


### Quorum deployment storage

| Name           | Description                                 | Value |
| -------------- | ------------------------------------------- | ----- |
| `storage.data` | Size for the data volume of the Quorum Node | `3Gi` |
| `storage.logs` | Size for the logs volume of the Quorum Node | `1Gi` |


----
Autogenerated from metadata using [Readme Generator for Helm](https://github.com/bitnami-labs/readme-generator-for-helm)