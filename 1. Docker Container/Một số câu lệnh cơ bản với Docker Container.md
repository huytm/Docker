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
