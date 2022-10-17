# PROJETO MEU MINIKUBE
### Documentação do processo de instalação do `Minikube` em uma VM

#### INFORMAÇÕES
- Alguns comandos são feitos pelo usuário comum e outros pelo super usuário (root/admin)
  - Comandos de super usuário serão com o **root**
  - Comandos do usuário comum serão com o **joao**

1. Baixar para VM a imagem de um Minikube
```ruby
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb
sudo dpkg -i minikube_latest_amd64.deb
```
![Comando Curl](https://user-images.githubusercontent.com/61891017/196175457-f80233a9-a499-4a0e-8ffc-afa945337ec3.png)

2. Iniciar o Minikube
```ruby
minikube start
```
![Fail](https://user-images.githubusercontent.com/61891017/196175975-6896772f-8475-4145-9199-60138b9394aa.png)
Aqui temos um `"erro"` por que não foram baixados os drivers necessários para rodar a aplicação

3. Baixar os Drivers
```ruby
apt install qemu-kvm libvirt-clients libvirt-daemon-system bridge-utils libguestfs-tools genisoimage virtinst libosinfo-bin
```
![Drivers_1](https://user-images.githubusercontent.com/61891017/196176768-af003d27-b137-44de-88e3-3318d3009508.png)
![Drivers_2](https://user-images.githubusercontent.com/61891017/196176865-3a8c5c72-bcd1-49c0-9d63-f38650419243.png)

4. Adicionar o usuário comum no grupo `"libvirt"`
```ruby
adduser [USER] libvirt
```
![image](https://user-images.githubusercontent.com/61891017/196177503-7f9e39b2-1a34-4cea-93ca-033bb9f61e11.png)

5. Iniciar o MInikube
```ruby
minikube start
```
![image](https://user-images.githubusercontent.com/61891017/196177661-0c14185d-9564-4ee5-b76f-1da1bb0c81f8.png)

6. 
