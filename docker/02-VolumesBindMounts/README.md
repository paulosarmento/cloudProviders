# publicacao

☁️ Docker – Persistência de Dados e Volumes

Hoje estudei um dos conceitos mais importantes do Docker: a natureza efêmera dos containers e como garantir a persistência de dados.

Aprendizados principais:

🔹 Por padrão, tudo que é criado dentro de um container é perdido quando ele é removido.
Isso acontece por causa do sistema de camadas (OverlayFS), onde o container usa uma camada de leitura e escrita temporária.

🔹 Para resolver isso, usamos:

Bind Mounts → montar pastas do host dentro do container (ideal para desenvolvimento)

Volumes Docker → gerenciados pelo Docker (recomendado para produção)

Exemplo prático:
✅ Executei um Nginx usando bind mount e consegui alterar o arquivo index.html no host e ver a mudança refletir no navegador em tempo real.
✅ Removi o container e confirmei que os dados persistiram quando usei volume corretamente.

Também aprendi a:

Criar e gerenciar volumes (docker volume create / ls / inspect)

Montar volumes em containers

Fazer backup e restauração de volumes usando containers temporários

Entendi quando usar cada abordagem:
✔ Bind Mounts → desenvolvimento
✔ Volumes → produção e dados sensíveis (banco de dados, aplicações)

Esse conceito é essencial para quem quer trabalhar com Cloud e DevOps, principalmente em ambientes com bancos de dados e aplicações reais.

Seguimos evoluindo um passo por dia 🚀

#Docker #CloudComputing #DevOps #Containers #Volumes #PersistenciaDeDados #AprendizadoContínuo #Tecnologia #Linux #AWS #CarreiraTech

# Bind mounts

## Comandos

docker run -p 8080:80 -d -v $(pwd)/my_nginx_html:/usr/share/nginx/html nginx

## Não recomendado

docker run -d -p 8080:80 --mount type=bind,source=$(pwd)/docker/02-VolumesBindMounts/my_nginx_html,target=/usr/share/nginx/html nginx

# Volumes

docker volume create my_volume
docker volume ls
docker volume inspect my_volume

docker run -d -p 8080:80 -v my_volume:/usr/share/nginx/html nginx
docker cp $(pwd)/my_nginx_html/index.html 1b309e96b8fc:/usr/share/nginx/html  
docker run -d -p 8080:80 --name mynginx -v my_volume:/usr/share/nginx/html nginx
docker cp $(pwd)/my_nginx_html/index.html mynginx:/usr/share/nginx/html

# busybox

Backup de um Volume
docker run --rm -v my_volume:/data -v $(pwd)/backup_host:/backup busybox tar czf /backup/backup.tar.gz /data

Restauração de um Volume
docker run --rm -v my_volume:/data -v $(pwd)/backup_host:/backup busybox tar xzf /backup/backup.tar.gz -C /
