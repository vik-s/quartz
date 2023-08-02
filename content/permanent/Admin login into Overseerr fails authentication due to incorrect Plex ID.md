---
title: "Admin login into Overseerr fails authentication due to incorrect Plex ID"
created: 2023-08-01 20:45
status: #permanent
tags: #homelab, #media
---


1. Turn off Overseer instance so DB is not in use
    
2. Installed a SQLite DB editor on my local system. For me I used `DB Browser for SQLite` on my mac
    
3. Copied just the main `db.sqlite3` file to my local system. This might not be necessary, but it did it
    
4. Opened `db.sqlite3` in my SQLite editor
    
5. Navigated to the `user` db table
    
6. Found my user and updated the missing plexId with the correct ID (I personally found this value in my tautulli database. I assume there are other places to find this Id as well
    
7. Saved my change to the row. When I did this, 2 other files were generated in the location I had copied the `db.sqlite3` file, they were `db.sqlite3-shm` and `db.sqlite3-wal`.
    
8. I backed up all 3 of these files in the overseer db folder (into a new backup directory outside of the db folder)
    
9. I then replaced all 3 of these files with my new copies
    
10. I started overseer again and the problem was resolved.”