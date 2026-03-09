# Linux File Permissions and Ownership

File permissions control who can read, write, or execute files and directories.

---

## View File Permissions

List files with permissions:

ls -l

Example output:

-rw-r--r-- 1 shashi devops 1200 Mar 9 file.txt

Explanation:

- rw- → owner permissions
- r-- → group permissions
- r-- → others permissions

---

## Permission Types

r → read  
w → write  
x → execute  

Example:

-rwxr-xr--

Owner → rwx  
Group → r-x  
Others → r--

---

## Change File Ownership

Change owner of file:

sudo chown username file

Example:

sudo chown shashi file.txt

---

## Change Owner and Group

sudo chown user:group file

Example:

sudo chown shashi:devops file.txt

---

## Change File Permissions

Using numeric method.

chmod 755 file

Explanation:

7 = rwx  
5 = r-x  
5 = r-x  

Owner → full access  
Group → read + execute  
Others → read + execute

---

## Common Permission Values

777 → full access  
755 → standard executable  
644 → standard file  

Example:

chmod 644 file.txt

---

## Change Permissions Recursively

Apply permissions to directory and contents:

chmod -R 755 directory/

---

## Special Permissions

### SUID

Allows user to run file with owner's permissions.

Example:

chmod u+s file

---

### SGID

Allows group ownership inheritance.

Example:

chmod g+s directory

---

### Sticky Bit

Used for shared directories like /tmp.

Example:

chmod +t directory

---

## Check Directory Permissions

Example:

ls -ld directory

---

## Default File Permissions (umask)

Check umask:

umask

Example output:

022

Meaning:

Files → 644  
Directories → 755

---

## Troubleshooting Permission Issues

Check ownership:

ls -l

Check directory permissions:

ls -ld directory

Fix ownership:

sudo chown -R user:group directory

Fix permissions:

chmod -R 755 directory

