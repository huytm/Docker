Docker Container là một container được khởi chạy từ Docker Image.


### 1. Chạy container từ image

Chạy một container từ image có sẵn từ Docker host. Nếu image không tồn tại, Docker sẽ tự động download từ Docker Registry (Mặc định sẽ là DockerHub)

```sh
docker run -itd <image_name>
```

*Ví dụ*

```sh
docker run -itd centos
docker ps
```

```
CONTAINER ID        IMAGE                 COMMAND             CREATED             STATUS              PORTS                  NAMES
62072d916d17        centos                "/bin/bash"         4 seconds ago       Up 2 seconds                               eager_herschel
```

### 2. Chạy container với một tên khác

Chạy Container với tên khác tên mặc định. Mặc định tên của Container sẽ sử dụng lib [này](https://github.com/moby/moby/blob/master/pkg/namesgenerator/names-generator.go) để sinh ra tên mặc định

```sh
docker run -itd --name <container_name> <image_name>
```

*Ví dụ*

```sh
docker run -itd --name huytm centos
```

```
CONTAINER ID        IMAGE                 COMMAND             CREATED             STATUS              PORTS                  NAMES
62072d916d17        centos                "/bin/bash"         4 seconds ago       Up 2 seconds                               eager_herschel
```

### 3. Chạy container với volume mount

Volume của Docker có 3 loại là **Volumes**, **Bind mounts**, **tmpfs mounts**. Ví dụ dưới đây sẽ chạy contaier với **Bind mounts** (Lưu ý thư mục */opt/test_mount* phải được tạo trước)

```sh
docker run -itd -v <host_path>:<container_path> <image_name>
hoặc
docker run -itd --mount type=bind,soure=<host_path>,target=<container_path> <image_name>
```

*Ví dụ*

```sh
docker run -itd -v /opt/test_mount:/mnt/ centos
hoặc
docker run -itd --mount type=bind,soure=/opt/test_mount,target=/mnt/ centos
```

*Kiểm tra lại*

```
"Mounts": [
            {
                "Type": "bind",
                "Source": "/opt/test_mount",
                "Destination": "/mnt",
                "Mode": "",
                "RW": true,
                "Propagation": "rprivate"
            }
        ],
```

### 4. Chạy container với port NAT

Khi khởi chạy container, tùy vào Image mà container sẽ LISTEN một số port. Để NAT các port này ra ngoài Docker host thì cần chạy container với option -p


```sh
docker run -itd -p <host_port>:<container_port> <image_name>
```

*Ví dụ*

```sh
docker run -itd -p 9000:80 httpd
```
