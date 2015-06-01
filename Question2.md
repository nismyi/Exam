#A.
#a)
etc/passwd file stores essential information, which is required during login. user account information. /etc/passwd is a text file, that contains a list of the system's accounts, giving for each account some useful information like user ID, group ID, home directory, shell, etc. It should have general read permission as many utilities, like ls use it to map user IDs to user names, but write access only for the superuser (root).
#b)
Our encrypted password is not stored in /etc/passwd file. It is stored in /etc/shadow file. /etc/shadow file stores actual password in encrypted format for user's account with additional properties related to user password i.e. it stores secure user account information. All fields are separated by a colon (:) symbol. It contains one entry per line for each user listed in /etc/passwd file Generally.
#c)
SETUID is a special type of file permissions given to a file. Normally in Linux/Unix when a program runs, it inherits access permissions from the logged in user. SUID is defined as giving temporary permissions to a user to run a program/file with the permissions of the file owner rather that the user who runs it. In simple words users will get file owner’s permissions as well as owner UID and GID when executing a file/program/command.
#d)
The chroot command changes its current and root directories to the provided directory and then run command, if supplied, or an interactive copy of the user's login shell. Please note that not every application can be chrooted.
The basic syntax is as follows:
chroot /path/to/new/root command
B.
ls -l is a file system agnostic method for displaying file attributes. It can only display those attributes which are required to be provided by the OS (such as UNIX permissions)
lsattr displays the extended file attributes for ext2 (and ext-like) file systems. This includes some of the information displayed by ls -l, as well information about data journaling, append-only, immutable, date-updating and etc
C.
Android permissions notification are so course-granied that they are almost completely uninformative in most cases. A common end result is that the onus of security is placed on the users, who are put in the position to make an uniformed choice to allow all the permissions requested by an application before installing it. This, compounded by the problem that application developers commonly request for privileges which are too broad for the application, lead to a complete violation of least privileges
A.
ACL's allow for permissions to be specified for specific other users, and groups.
Standard unix permissions only allow for permissions to be declared for the owner, owner's group, and everyone else.
B.
owner's group, and everyone else rui = real user id. This is the identity of the logged in user who launches programs. Ruid is set when the user logs in, and can only be changed by a root user. Also process signalling is controlled by ruid . Process X can only signal process Y if process X has the same ruid as Y, or is root ruid.
Euid refers to effective user id, which is the UID used to judge privilege and access permission. in most cases, this is the same as ruid. But if a program were flagged with the setuid bit, then when it is executed, it is assigned the euid of the owner of the program. Also the setuid() or seteuid() functions allow for the EUID to be changed to the ID designated as parameters.
C.
An attacker may erase specific logs to cover his/her tracks. Also an attacker could use a rootkit to sustain covert access. Also an attacker might hide their files in hidden directories (those that start with '.').
