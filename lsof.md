 lsof commands.
Lsof stands for ls open files, which will list all the open files in the system.
The open files include network connection, devices and directories. The
output of the lsof command will have the following columns:
o COMMAND process name.
o PID process ID
o USER Username 
o FD file descriptor
o TYPE node type of the file
o DEVICE device number
o SIZE file size
o NODE node number
o NAME full path of the file name.
View all open files of the system
Execute the lsof command without any parameter as shown below.
# lsof | more
COMMAND PID USER FD TYPE DEVICE SIZE NODE
NAME
init 1 root cwd DIR 8,1 4096 2 /
init 1 root rtd DIR 8,1 4096 2 /
init 1 root txt REG 8,1 32684 983101 /sbin/init
init 1 root mem REG 8,1 106397 166798 /lib/ld2.3.4.so

init 1 root mem REG 8,1 1454802 166799
/lib/tls/libc-2.3.4.so
init 1 root mem REG 8,1 53736 163964
/lib/libsepol.so.1
init 1 root mem REG 8,1 56328 166811
/lib/libselinux.so.1
init 1 root 10u FIFO 0,13 972 /dev/initctl
migration 2 root cwd DIR 8,1 4096 2 /
skipped…
The lsof command by itself without may return lot of records as output,
which may not be very meaningful except to give you a rough idea about how 

many files are open in the system at any given point of view as shown below.
# lsof | wc -l
3093
View open files by a specific user
Use lsof –u option to display all the files opened by a specific user.
# lsof –u ramesh
vi 7190 ramesh txt REG 8,1 474608
475196 /bin/vi
sshd 7163 ramesh 3u IPv6 15088263
TCP dev-db:ssh->abc-12-12-12-12.socal.res.rr.com:2631
(ESTABLISHED)
A system administrator can use this command to get some idea on what users
are executing on the system.
List Users of a particular file
If you like to view all the users who are using a particular file, use lsof as
shown below. In this example, it displays all users who are currently using vi.
# lsof /bin/vi
COMMAND PID USER FD TYPE DEVICE SIZE NODE NAME
vi 7258 root txt REG 8,1 474608 475196 /bin/vi
vi 7300 ramesh txt REG 8,1 474608 475196 /bin/vi 
