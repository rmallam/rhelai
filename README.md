 aws iam create-role --role-name vmimport --assume-role-policy-document "file://vmimport-trust-policy.json"

 aws iam put-role-policy --role-name vmimport --policy-name vmimport --policy-document "file://vmimport-role.json"

aws ec2 import-image --description "My server disks" --disk-containers "file://containers.json"
{
    "Description": "My server disks",
    "ImportTaskId": "import-ami-0dbf1e9f04fadff0a",
    "Progress": "1",
    "SnapshotDetails": [
        {
            "Description": "My Server OVA",
            "DiskImageSize": 0.0,
            "Format": "RAW",
            "Url": "s3://aifedora/fedora.raw",
            "UserBucket": {
                "S3Bucket": "aifedora",
                "S3Key": "fedora.raw"
            }
        }
    ],
    "Status": "active",
    "StatusMessage": "pending"