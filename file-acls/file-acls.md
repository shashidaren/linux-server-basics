# Linux File ACLs (Access Control Lists)

ACLs allow more fine-grained permissions than traditional Linux permissions.

Standard permissions allow access for:

owner  
group  
others  

ACLs allow specific permissions for individual users or groups.

---

## Check ACL Support

Verify filesystem supports ACL:

mount | grep acl

---

## Install ACL Tools

RHEL / Rocky / Alma:

sudo dnf install acl

---

## View ACLs

Use getfacl:

getfacl filename

Example:

getfacl file.txt

---

## Set ACL for a User

Grant read permission:

setfacl -m u:username:r file.txt

Example:

setfacl -m u:shashi:r file.txt

---

## Grant Read and Write Permission

setfacl -m u:username:rw file.txt

Example:

setfacl -m u:shashi:rw file.txt

---

## Set ACL for a Group

setfacl -m g:groupname:rw file.txt

Example:

setfacl -m g:devops:rw file.txt

---

## Remove ACL for User

setfacl -x u:username file.txt

Example:

setfacl -x u:shashi file.txt

---

## Remove All ACLs

setfacl -b file.txt

---

## Set Default ACL for Directory

Default ACLs apply to new files created in the directory.

setfacl -d -m u:username:rw directory/

Example:

setfacl -d -m u:shashi:rw project/

---

## Recursive ACL Application

Apply ACL recursively:

setfacl -R -m u:username:rw directory/

---

## View Directory ACLs

getfacl directory/

---

## Check ACL Indicator

List files with ACL:

ls -l

Example:

-rw-rw-r--+ file.txt

The + indicates ACL is present.

---

## Troubleshooting ACLs

Check ACL:

getfacl file.txt

Remove all ACLs:

setfacl -b file.txt

Verify permissions:

ls -l file.txt

