**Instruções Dockerfile**
<p>As instruções abaixo permite que possamos criar uma imagem personalizada: ⬇️</p>

</br>
<p>Essa instrução diz qual imagem e tag deve ser feito o download.</p>
<pre>
<code>FROM nome_da_imagem:tag</code>
</pre>

</br>
<p>Essa instrução executa o comando assim que o download da imagem for realizado. Podemos executar mais de um comando adicionando o <strong>&&</strong> .</p>
<pre>
<code>RUN comando_deve_ser_executado</code>
<code>RUN comando_1 && comando_2 && comando_3</code>
</pre>

</br>
<p>Essa instrução cria um diretório dentro do container, e automaticamente nos coloca dentro dessa pasta.</p>
<pre>
<code>WORKDIR caminho_do_diretorio</code>
</pre>

</br>
<p>Essa instrução permite copiar um arquivo de dentro da máquina para dentro do container especificando o diretório desse arquivo.</p>
<pre>
<code>COPY nome_do_arquivo diretório_do_arquivo</code>
</pre>

</br>
<p>Essa instrução será executada como o ultimo comando depois que o container estiver pronto, podendo ser alterado na hora de criar o container. No exemplo, estou executando o comando <strong>echo Hello World</strong></p>
<pre>
<code>CMD ["echo", "Hello World"]</code>
</pre>

</br>
<p>Essa instrução será executada como o ultimo comando depois que o container estiver pronto, não podendo ser alterado, pois é um comando fixo, e recebendo como parametro o comando CMD. No exemplo, estou executando o comando <strong>echo Hello World</strong></p>
<pre>
<code>ENTRYPOINT ["echo", "Hello World"]</code>
</pre>

**Exemplo Dockerfile**

FROM ubuntu:latest

WORKDIR /app

RUN apt-get update && apt-get install vim -y

COPY html /usr/share/nginx/html

ENTRYPOINT [ "echo", "Hello World"]

CMD [ "Hello World" ]