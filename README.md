# Docker vsftpd server

To use this image simply build up using docker-compose

## Passive mode
To use passive mode, you have to put the server IP inside the `vsftpd/vsftpd.conf` file

## Users
The default user is `admin` with password `password`, maybe you want to change it

### Manage users
Users are stored in the `vsftpd/passwd` file,
to add a user run:

```sh
echo "[USERNAME]:$(openssl passwd -1 [PASSWORD])" >> passwd
```

Inside the `vsftpd` folder



### Home directory
Each user has a home directory matching his name.  All the folders are stored inside `/home/virtual/[USER NAME]` so you can mount to this path every volume you want (to do that, change the `docker-compose.yml` file)

## Credits

Thanks to [vimagick](https://github.com/vimagick/dockerfiles/tree/master/vsftpd) for his Docker image