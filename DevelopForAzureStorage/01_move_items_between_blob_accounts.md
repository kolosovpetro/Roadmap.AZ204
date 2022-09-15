# Move items in Blob storage between storage accounts or containers

Requirements: [Download AzCopy](https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy-v10)

- Copy a Blob within the Azure CLI: `az storage blob copy start
  --source-account-name "storagepluralsight01"
  --source-account-key "00000000"
  --source-container "images"
  --source-blob "thomas.jpg"
  --account-name "storagepluralsight02"
  --account-key "00000000"
  --destination-container "pictures"
  --destination-blob "thomas.jpg"`

- Copy a Container within the Azure CLI: `az storage blob copy start-batch
  --source-account-name "storagepluralsight01"
  --source-account-key "00000000"
  --source-container "images"
  --account-name "storagepluralsight02"
  --account-key "00000000"
  --destination-container "pictures"`

- Upload local folder using
  AzCopy: `azcopy copy "C:\Documents" "https://storagepluralsight01.blob.core.windows.net/[container]?[SAS]" --recursive=true`

- Copy a single blob using
  AzCopy: `azcopy copy "https://source.blob.core.windows.net/[container]/[blob]?[SAS]" "https://destination.blob.core.windows.net/[container]/[blob]?[SAS]`

- Copy blobs between containers using
  AzCopy: `azcopy copy "https://source.blob.core.windows.net/[container]?[SAS]" "https://destination.blob.core.windows.net/[container]?[SAS]" --recursive=true`

- Copy containers between storage accounts using
  AzCopy: `azcopy copy "https://source.blob.core.windows.net/?[SAS]" "https://target.blob.core.windows.net/?[SAS]" --recursive=true`
