**Comandos**

</br>
<p>Essa instrução verifica se já existe alguma chave gpg cadastrada.</p>
<pre>
<code>$ gpg --list-secret-key --keyid-form LONG</code>
</pre>

</br>
<p>Essa instrução gera uma chave gpg. Gerar a chave no padrã RSA (opção 1). Gerar a chamve com o tamanho 4096 bits. Gerar a chave com o tempo que que achar necessário (1y = 1 ano, 1m = 1 mes, 0 = nunca expirada a chave). Colocar o nome e email que está configurado seu git, não precisa colocar comentário. Confirmar a configuração com a letra o (ó). Digitar uma senha para acessar a chave (qualquer senha).</p>
<pre>
<code>$ gpg --full-generate-key</code>
</pre>

</br>
<p>Essa instrução mostra o endereço public da chave gpg.</p>
<pre>
<code>$ gpg --armor --export id_da_chave</code>
</pre>

</br>
<p>Essa instrução vai utilizar a chave cadastrada para assinar os commits.</p>
<pre>
<code>$ git config --global user.signingkey id_da_chave</code>
</pre>

</br>
<p>Essa instrução deve ser feita para a chave cadastrada funcionar.</p>
<pre>
<code>$ export GPG_TTY=$(tty)</code>
</pre>

</br>
<p>Essa instrução configura que todos os commits deverão usar a assinatura GPG. O parametro --global faz com que adicione essa instrução em qualquer repositório git.</p>
<pre>
<code>$ git config --global commit.gpgsign true</code>
</pre>

</br>
<p>Essa instrução configura que todas as tags deverão usar a assinatura GPG. O parametro --global faz com que adicione essa instrução em qualquer repositório git.</p>
<pre>
<code>$ git config --global tag.gpgSign true</code>
</pre>

</br>
<p>Essa instrução permite editar as configurações da chave GPG.</p>
<pre>
<code>$ gpg --edit-key id_da_chave</code>
<code><strong>adduid: </strong>Cadastrar um novo nome e id</code>
<code><strong>uid 2: </strong>Seleciona o usuário dois cadastrado</code>
<code><strong>trust: </strong>Selecionar qual o nivel de confiança desse usuário. Confirmar a ação com Y</code>
<code><strong>save: </strong>Salva as configurações feitas</code>
</pre>

**Adicionar no git hub a chave public cadastrada no PC**

<ul>
<li>Clicar em "settings" na flag down do lado da imagem do seu avatar.</li>
<li>Clicar na opção "SSH and GPG keys".</li>
<li>Clicar no botão "New GPG key".</li>
<li>Colocar a chave public gerada pelo comando <strong>gpg --armor --export id_da_chave</strong> e clicar em "Add GPG key".</li>
</ul>