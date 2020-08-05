# simple-btrfs-sync
Syncs btrfs snapshots from one folder to another.

A small script used for syncing btrfs snapshots between two folders. Can be used to backup snapshots from one hard drive to another. Will automatically delete snapshots which are present in the destination folder but not in the source folder. Will always use the latest snapshot in the destination folder as parent for the next incoming snapshot.


## Goals

Use btrfs send ... | btrfs recieve ...
As a simple and efficient way of backup snapper snapshots to a local mounted backup or a remote backup.

## Usage

1. Make the script executable:

`chmod +x ./simple-btrfs-sync`
or
`python3 simple-btrfs-sync`

2. Run it with `-n` or `--no_action` to see what it will do without actually syncing:

`./simple-btrfs-sync -i <src_folder> -o <dst_folder> -n`

3. If the output looks like you would expect it, actually perform the sync:

usage: simple-btrfs-sync [-h] -i INDIR -o OUTDIR [-d DELETE_LARGEST] [-n]

example

simple-btrfs-sync -i snapshot_root -o backup_snapshot_roo0t -d delete_backup_snapshots which do not exist in snapshot source
`simple-btrfs-sync -i / -o /backup/backup-root  -d`
`simple-btrfs-sync -i /home -o /backup/backup-home  -d`

Seperate directories for exmpale backup-root and backup-home should be used for each btrfs subvolume set to the same backup btrfs

##Notes
The script has only be tested for locally mounted storage and not remote ssh connected storage.

Keeping additional backup snapshots in the btrfs source volume has not been verified. And to be added later.
