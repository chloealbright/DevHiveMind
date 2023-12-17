---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Your notes cover various aspects of file systems, permissions, and commands. Here's a refined version:

- **File Types:**
  - Regular files
  - Directories
  - Symbolic (soft) links/hard links
  - Pipe
  - Block/character
  - Socket

- **Example File Listings:**
  - `-rw-r--r-- 1 root root 718 Aug 31 17:19 wget-log`
  - `drwxr-xr-x 2 jac jac 4.0K Sep 8 20:46 .wakatime/`

- **File Metadata and Hard Link Count:**
  - `stat` command displays file metadata.
  - Hard link count is usually 1 for files, 2 for directories, and more for subdirectories.

- **Default Permissions and Umask:**
  - Default permission: 666
  - `umask` affects file permissions.

- **Chmod Modifiers and Flags:**
  - Using numbers (e.g., `chmod 755 file`) versus flags (e.g., `chmod +x file`).

- **Chmod Commands:**
  - `chmod -v u+x`: `-v` shows the changes.
  - `chmod -v +x file`

- **Umask and Directory Operations:**
  - `umask 007`
  - `mkdir upper/{d1,d2}/file`
  - `touch upper/{d1,d2}/file`
  - `ls -lr upper`
  - `chmod -vR a+x upper`

These refined notes aim to provide a clearer and organized overview of the concepts you've mentioned. If you have specific points that still need clarification or expansion, feel free to ask!