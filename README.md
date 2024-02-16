# self-hosted
> part of home lab

### Docker
1. portainer
```bash
mkdir portainer && cd portainer

docker run -d \
-p 9000:9000 \
-p 8000:8000 \
--restart always \
-v /var/run/docker.sock:/var/run/docker.sock \
-v ./data:/data \
--name portainer-ce portainer/portainer-ce
```
2. minio
```bash
# {{ user }} and {{ password }} should change 
mkdir minio && cd minio

docker run -d -p 9100:9000 -p 9190:9090 --name minio \
  -e "MINIO_ROOT_USER={{ user }}" \
  -e "MINIO_ROOT_PASSWORD={{ password }}" \
  -v ./data:/data \
  --restart=always \
  minio/minio server /data --console-address ':9090'
```
3. 
