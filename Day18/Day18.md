# Day 18: Copy Data to an Azure Blob Storage Container

# Step1: Copy data to Azure Blob Container via CLI

az storage blob upload \
  --account-name datacenterst24005 \
  --container-name datacenter-blob-7666 \
  --name datacenter.txt \
  --file /tmp/datacenter.txt \
  --auth-mode login

#Expected Output:

Finished[#############################################################]  100.0000%
{
  "client_request_id": "c65ba82e-4a24-11f1-b9ff-16606b9a6f25",
  "content_md5": "Lu7zilatbGguzSz2Ecn5IQ==",
  "date": "2026-05-07T14:55:24+00:00",
  "encryption_key_sha256": null,
  "encryption_scope": null,
  "etag": "\"0x8DEAC48AB81F831\"",
  "lastModified": "2026-05-07T14:55:24+00:00",
  "request_id": "3329d266-601e-0080-6131-de7528000000",
  "request_server_encrypted": true,
  "version": "2022-11-02",
  "version_id": null
}

# Step2: Verify the file

az storage blob list \
  --account-name datacenterst24005 \
  --container-name datacenter-blob-7666 \
  --output table \
  --auth-mode login
