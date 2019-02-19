### 1. Show list các Image

```
docker images
```

*Kết quả*

```
REPOSITORY            TAG                 IMAGE ID            CREATED             SIZE
huytm/centos7-httpd   latest              97ba637ff1df        11 hours ago        457MB
httpd                 latest              d3a13ec4a0f1        6 days ago          132MB
centos                centos7             1e1148e4cc2c        2 months ago        202MB
centos                latest              1e1148e4cc2c        2 months ago        202MB
```

### 2. Show metadata của Image

```
docker inspect <REPOSITORY>
```

Ví dụ

```
docker inspect httpd
```


### 3. Pull một image từ Registry

```
docker pull <image>
```

### 4. Build image từ Dockerfile

```
docker build -t  <image_name> <path_to_Dockerfile>
```

*Ví dụ*

```
docker build -t huytm_centos .
```

### 5. Xóa một image

Chú ý: Không container nào đang sử dụng image

```
docker rmi  <REPOSITORY> 
```

*Ví dụ*

```
docker rmi centos 
```

### 6. Xóa tất cả image

```
docker rmi  $(docker images -a -q)
```
