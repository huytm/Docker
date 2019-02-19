Các câu lệnh quản lý Docker Container

### 1. Tạo một container từ Image

Tạo một container từ image có sẵn từ Docker host. Nếu image không tồn tại, Docker sẽ tự động download từ Docker Registry (Mặc định sẽ là DockerHub)

```sh
docker create -it <image_name>
```

*Ví dụ*

```sh
docker create -it centos
```

*Kiểm tra lại*

```
docker ps -a 
```

```
CONTAINER ID        IMAGE               COMMAND              CREATED             STATUS              PORTS                  NAMES
099ad593bee5        centos              "/bin/bash"          4 seconds ago       Created                                    competent_wiles
```


### 2. Kiểm tra các container đang running 

Kiểm tra các container đang running

```sh
docker ps 
```

```
CONTAINER ID        IMAGE               COMMAND              CREATED             STATUS              PORTS                  NAMES
cbd33af9b6a2        httpd               "httpd-foreground"   7 minutes ago       Up 7 minutes        0.0.0.0:9000->80/tcp   confident_robinson
2912045c7c59        centos              "/bin/bash"          16 minutes ago      Up 16 minutes                              practical_dhawan
2527879365ea        centos              "/bin/bash"          23 minutes ago      Up 23 minutes                              pedantic_austin
7ddaa63f3536        centos              "/bin/bash"          29 minutes ago      Up 29 minutes                              xenodochial_hugle
963c16576e5c        centos              "/bin/bash"          33 minutes ago      Up 33 minutes                              huytm
```

### 3. Kiểm tra tất cả các container 

Kiểm tra các tất cả các container

```sh
docker ps -a
```

```
CONTAINER ID        IMAGE               COMMAND              CREATED             STATUS              PORTS                  NAMES
099ad593bee5        centos              "/bin/bash"          3 minutes ago       Created                                    competent_wiles
cbd33af9b6a2        httpd               "httpd-foreground"   9 minutes ago       Up 9 minutes        0.0.0.0:9000->80/tcp   confident_robinson
2912045c7c59        centos              "/bin/bash"          18 minutes ago      Up 18 minutes                              practical_dhawan
2527879365ea        centos              "/bin/bash"          25 minutes ago      Up 25 minutes                              pedantic_austin
7ddaa63f3536        centos              "/bin/bash"          31 minutes ago      Up 31 minutes                              xenodochial_hugle
963c16576e5c        centos              "/bin/bash"          35 minutes ago      Up 35 minutes                              huytm
```

### 4. Kiểm tra thông tin metadata của container

Kiểm tra metadata của container

```sh
docker inspect <CONTAINER ID>
hoặc 
docker inspect <NAMES>
```

*Ví dụ*

```sh
docker inspect 2912045c7c59
hoặc
docker inspect huytm
```

### 5. Start container

Start container

```sh
docker start <CONTAINER ID>
hoặc 
docker start <NAMES>
```

*Ví dụ*

```sh
docker start 2912045c7c59
hoặc
docker start huytm
```


### 6. Stop container

Stop container

```sh
docker stop <CONTAINER ID>
hoặc 
docker stop <NAMES>
```

*Ví dụ*

```sh
docker stop 2912045c7c59
hoặc
docker stop huytm
```

### 7. Stop tất cả c ác container

```
docker stop $(docker ps -a -q)
```

### 8. Restart container

Restart container

```sh
docker restart <CONTAINER ID>
hoặc 
docker restart <NAMES>
```

*Ví dụ*

```sh
docker restart 2912045c7c59
hoặc
docker restart huytm
```

### 9. Xóa container

Xóa container

```sh
docker rm <CONTAINER ID>
hoặc 
docker rm <NAMES>
hoặc force xóa container
docker rm f <CONTAINER ID>
```

*Ví dụ*

```sh
docker rm 2912045c7c59
hoặc
docker rm huytm
```

### 10. Xóa tất cả các container

```
docker stop  $(docker ps -a -q)
docker rm  $(docker ps -a -q)
```

