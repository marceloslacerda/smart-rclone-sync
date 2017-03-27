# smart-rclone-sync
A simple script for syncing files with rclone more intelligently

## What does it do?

Given two directories *A* and *B* where *B* is a directory in a remote directory *re* and each has the following tree structure:

    A/
    .... a.txt
    .... b.txt
    .... c.txt
    
    B/
    .... b.txt
    .... c.txt
    .... d.txt
    
Where *b.txt* is the same in *A* and *B* and *c.txt* is different in the two directories,
    
Running *smart-rclone-sync* like this

$ smart-rclone-sync A/ re:/B/

Will produce the following output

    Sending file a.txt from A/ to re:/B/
    1 files uploaded to remote
    Sending file d.txt from re:/B/ to A/
    1 files downloaded from remote
    The following files could not be synced
    c.txt
    
## Requires

python >= 3.3
