# simple-btrfs-sync
Syncs btrfs snapshots from one folder to another.

A small script used for syncing btrfs snapshots between two folders. Can be used to backup snapshots from one hard drive to another. Will automatically delete snapshots which are present in the destination folder but not in the source folder. Will always use the latest snapshot in the destination folder as parent for the next incoming snapshot.

## Usage

1. Make the script executable
`chmod +x ./simple-btrfs-sync`

2. Run it as a dry run to see what it will do withou actually doing something
`./simple-btrfs-sync <src_folder> <dst_folder> -d`

3. If the output looks like you would expect it actually perform the sync
`./simple-btrfs-sync <src_folder> <dst_folder>
