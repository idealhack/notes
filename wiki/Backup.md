# Backup

## Tools

### Time Machine

### rsync

    rsync -av user@host:/src .

rsync through ssh tunnel:

    rsync -av -e "ssh -A root@proxy ssh" ./src root@target:/dst

### Deduplication Tools

- [BorgBackup – Deduplicating archiver with compression and authenticated encryption](https://www.borgbackup.org/)
- [bup, it backs things up!](https://bup.github.io/)

## Resources

- [Full system backup with rsync - ArchWiki](https://wiki.archlinux.org/index.php?title=Full_system_backup_with_rsync&redirect=no)
