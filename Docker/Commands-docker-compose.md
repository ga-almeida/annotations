**Comandos**
<p>Comandos utilizados para gerenciar o docker-compose na máquina:</p>

</br>
<p>Executa o arquivo docker-compose.yaml para subir todos os containers do arquivo.</p>
<pre>
<code>$ docker-compose up</code>
</pre>

</br>
<p>Executa o arquivo docker-compose.yaml removendo todos os containers do arquivo.</p>
<pre>
<code>$ docker-compose down</code>
</pre>

</br>
<p>Mostra a lista de containers que foram gerados pelo docker-compose.</p>
<pre>
<code>$ docker-compose ps</code>
</pre>

</br>
<p>Executa o arquivo docker-compose.yaml para subir todos os containers do arquivo. No exemplo está sendo executado no modo em que libera o terminal por conta do parametro -d e refaz a build dos container pelo parametro --build.</p>
<pre>
<code>$ docker-compose up -d --build</code>
</pre>