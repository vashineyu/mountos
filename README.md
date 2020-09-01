# mountos
scripts for mounting object storage at TWCC clusters/VMs.

### Prerequisite
* [goofys](https://github.com/kahing/goofys)
* [aws-cli](https://github.com/aws/aws-cli)

### Usage
To mount volume. (no root required)
```bash
$ export AWS_ACCESS_KEY_ID=[YOUR_ACCESS_KEY_ID]
$ export AWS_SECRET_ACCESS_KEY=[YOUR_ACCESS_KEY]

$ ./goofys --file-mode=0644 --dir-mode=0755 --endpoint https://cos.twcc.ai [BUCKET_NAME] [MOUNT_POINT]
```

To unmount volume.
```bash
$ fusermount -u [MOUNT_POINT]
```

### Profiles for profiles
Edit ~/.aws/credentials
```bash
[default]
aws_access_key_id=KEYID01
aws_secret_access_key=KEYSECRET01

[twcc]
aws_access_key_id=KEYID02
aws_secret_access_key=KEYSECRET02
```

Or you can export your credentials file by `export /mnt/deep-learning/usr/seanyu/home/maintenance/s3/credentials`
