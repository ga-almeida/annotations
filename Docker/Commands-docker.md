**Comandos**
<p>Comandos utilizados para gerenciar o docker na máquina:</p>

</br>
<p>Lista todos os containers ativos que estão na máquina.</p>
<pre>
<code>$ docker ps</code>
</pre>

</br>
<p>Lista todos os containers na máquina independentemente se estão ativos ou não.</p>
<pre>
<code>$ docker ps -a</code>
</pre>

</br>
<p>Permite criar um container de forma simples a partir de alguma imagem, exemplo da iamgem (Hellow World).</p>
<pre>
<code>$ docker run hello-world</code>
</pre>

</br>
<p>O parametro -it, permite criar um container de forma interativa, onde assim que o contaienr for criado, será liberado para ser digitado algo no terminal.</p>
<pre>
<code>$ docker run -it ubunto bash</code>
</pre>

</br>
<p>O parametro --rm, permite criar um container que será removido assim que ele for desativado.</p>
<pre>
<code>$ docker run -it --rm ubunto bash</code>
</pre>

</br>
<p>Esse comando faz com que um container seja ativado.</p>
<pre>
<code>$ docker start nome_do_container_ou_ID</code>
</pre>

</br>
<p>Esse comando faz com que um container seja desativado.</p>
<pre>
<code>$ docker stop nome_do_container_ou_ID</code>
</pre>

</br>
<p>Permite criar um container a partir de alguma imagem com o redirencionamento entre as portas da máquina e container. O parametro -p é responsável por esse redirencionamento. Onde a porta do lado esquerdo é a porta da máquina e a do lado direito é a porta do container.</p>
<pre>
<code>$ docker run -p 8080:80 nome_da_imagem</code>
</pre>

</br>
<p>Permite criar um container a partir de alguma imagem em modo desatachado. O parametro -d é responsável por isso. Dessa forma, assim que o container for criado, não é necessário estar com o terminal aberto para o container permancer ativo.</p>
<pre>
<code>$ docker run -d nome_da_imagem</code>
</pre>

</br>
<p>Permite remover um container da máquina.</p>
<pre>
<code>$ docker rm nome_do_container_ou_ID</code>
</pre>

</br>
<p>O parametro -f permite forçar a remoção de um container da máquina mesmo que ele esteja ativo.</p>
<pre>
<code>$ docker rm nome_do_container_ou_ID -f</code>
</pre>

</br>
<p>O parametro --name permite criar um container e no momento da criação atribuir qualquer nome a ele, no exemplo o container está recebendo o nome de nginx.</p>
<pre>
<code>$ docker run -d --name nginx nome_da_imagem</code>
</pre>

</br>
<p>Esse comando permite executar algum comando dentro do container, no exemplo estamos executando o comando ls dentro do container.</p>
<pre>
<code>$ docker exec nome_do_container ls</code>
</pre>

</br>
<p>Esse comando junto com o parametro -it permite executar algum comando dentro do container, no exemplo estamos executando o comando bash dentro do container de forma interativa, ou seja estamos utilizando o próprio termional dentro do container.</p>
<pre>
<code>$ docker exec -it nome_do_container bash</code>
</pre>

</br>
<p>O parametro -v permite eu mapear alguma pasta/arquivo da máquina para alguma pasta/arquivo dentro do container. No exemplo está sendo apontado o caminho <strong>~/projects/annotations/docker/html/</strong> da máquina para o caminho <strong>/usr/share/nginx/html</strong> do container.</p>
<pre>
<code>$ docker run -d --name nginx -p 8080:80 -v ~/projects/annotations/docker/html/:/usr/share/nginx/html nome_da_imagem</code>
</pre>

</br>
<p>O parametro --mount permite eu mapear alguma pasta/arquivo da máquina para alguma pasta/arquivo dentro do container de uma forma mais explicita, onde o -v cria a pasta no container e o --mount não cria a pasta caso não exista. No exemplo está sendo apontado o caminho <strong>~/projects/annotations/docker/html/</strong> da máquina para o caminho <strong>/usr/share/nginx/html</strong> do container.</p>
<pre>
<code>$ docker run -d --name nginx -p 8080:80 --mount type=bind,source=~/projects/annotations/docker/html,target=/usr/share/nginx/html nome_da_imagem</code>
</pre>

</br>
<p>Esse comando permite criar um volume, no exemplo está sendo criado com o nome meuvolume.</p>
<pre>
<code>$ docker volume create meuvolume</code>
</pre>

</br>
<p>Esse comando permite mostrar todos os volumes.</p>
<pre>
<code>$ docker volume ls</code>
</pre>

</br>
<p>Esse comando permite inspecionar o volume.</p>
<pre>
<code>$ docker volume inspect nome_do_volume</code>
</pre>

</br>
<p>Esse comando permite mapear algum volume criado para dentro de um container, no exemplo o volume que foi criado está sendo mapeado para /app dentro do container.</p>
<pre>
<code>$ docker run -d --name nginx -p 8080:80 --mount type=volume,source=nome_do_volume,target=/app nome_da_imagem</code>
</pre>

</br>
<p>Esse comando permite remover todos volumes que não estão sendo utilizados.</p>
<pre>
<code>$ docker volume prune</code>
</pre>

</br>
<p>Esse comando permite fazer o download de uma imagem.</p>
<pre>
<code>$ docker pull nome_da_imagem</code>
</pre>

</br>
<p>Esse comando permite listar todas as imagens que estão na máquina.</p>
<pre>
<code>$ docker images</code>
</pre>

</br>
<p>Esse comando permite remover alguma imagem que está na máquina.</p>
<pre>
<code>$ docker rmi nome_da_imagem</code>
</pre>

</br>
<p>Esse comando permite subir no repositório do docker hub a imagem personalizada a partir de um Dockerfile. O parametro -t representa qual tag e o nome da imagem vai ser feito o build no Docker hub. No exemplo abaixo, está sendo feito a build com a tag <strong>gabrielsantos</strong> e o nome da imagem como <strong>nginx-com-vim</strong></p>
<pre>
<code>$ docker build -t gabrielsantos/nginx-com-vim:latest .</code>
</pre>

</br>
<p>Esse comando remove todos os containers eles estando ativos ou não.</p>
<pre>
<code>$ docker rm $(docker ps -a -q) -f</code>
</pre>

</br>
<p>Esse comando permite fazer login na conta do docker hub.</p>
<pre>
<code>$ docker login</code>
</pre>

</br>
<p>Esse comando permite fazer o upload no docker hub. No exemplo, está sendo feito o upload no usuário gabrielsantos, e o nome da imagem vai ser nginx-com-vim.</p>
<pre>
<code>$ docker push gabrielsantos/nginx-com-vim/</code>
</pre>

</br>
<p>Esse comando permite listar todas as networks.</p>
<pre>
<code>$ docker network ls</code>
</pre>

</br>
<p>Esse comando permite remover todas as networks que não estão sendo utilizadas.</p>
<pre>
<code>$ docker network prune</code>
</pre>

</br>
<p>Esse comando permite inspecionar a network e verificar quais container estão conectados naquela rede. No exemplo, estamos inspecionando a network minharede.</p>
<pre>
<code>$ docker network inspect minharede</code>
</pre>

</br>
<p>Esse comando permite entrar com o terminal bash no container.</p>
<pre>
<code>$ docker attach nome_do_container</code>
</pre>

</br>
<p>Esse comando permite criar uma rede. No exemplo, está sendo criado uma rede do tipo bridge com o nome minharede.</p>
<pre>
<code>$ docker network create --driver bridge minharede</code>
</pre>

</br>
<p>Esse comando permite adicionar uma network ao container no momento de criação do mesmo. No exemplo, está sendo criado um container com a network minharede.</p>
<pre>
<code>$ docker run -d -it --name ubuntu --network minharede bash</code>
</pre>

</br>
<p>Esse comando permite conectar algum container em uma network. No exemplo, está sendo conectado o container ubuntu na network minharede.</p>
<pre>
<code>$ docker network connect minharede ubuntu</code>
</pre>