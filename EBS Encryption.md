- You have nothing to do
- has minimal latency impact
- Uses KMS(AES-256) keys

#### What's Encrypted?
1. Data inside
2. Data in flight 
3. All snapshots
4. Volume created from snapshots

#### Encrypt an Unencrypted EBS Volume
1. Take a snapshot. 
2. ==Copy Snapshot,== while copying enable encryption. 
3. Now use the copy of snapshot to create a volume
4. The end volume will be encrypted.