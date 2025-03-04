# AzureCloud-ServidorFiveM
Manual de como subir seu servidor de FiveM para nuvem, utilizando serviços de cloud da Azure.

---------------------------------------------------------------
CRIAÇÃO DA VM
----------------------------------------------------------------

No Azure, vamos buscar por MÁQUINAS VIRTUAIS e clicar em adicionar. Em seguida, clicamos em maquina virtual.

![1-AdicionarVM](https://user-images.githubusercontent.com/58913096/104278811-f6087680-5487-11eb-829f-6d6f0b47b21b.png)


Quando entrarmos na configuração da VM, vamos em, grupo de recursos, criar novo e depois colocamos o nome do seu grupo de recursos e clique em adicionar.

![2-CriandoGR](https://user-images.githubusercontent.com/58913096/104278939-310aaa00-5488-11eb-9893-daf055fdf4c6.png)


Preencha os dados da sua maquina: 
<p>1- Nome: Coloque o nome do seu servidor de FiveM.</p>
<p>2- Região: deixe a recomendada pela Azure.</p>
<p>3- Imagem: Imagem vai ser o sistema operacional que vamos utilizar para rodar a nossa base(rp). Como ela não roda no Linux por conta do HEIDISQL, recomendamos que você utilize o windows R2 server (se você tiver um conhecimento mais avançado). Caso contrario, utilize o Windows 10 Desktop.</p>
<p>4- Tamanho: Para rodar um servidor com 64 pessoas, selecione a opção Standar_ds1_v2 - 1 vcu, 3.5gb (ram). No plano gratuito, vem uma configuração mais baixa. Porém você vai conseguir rodar a base no mesmo jeito, com mais dificuldade na hora de configuração do seu servidor (server.cfg, resources, navegador e HEIDISQL).</p>

<p>#######ATENÇÃO########</p>
<p>5- Admin: Nome de usuario e senha da sua MÁQUINA VIRTUAL, não esqueça de forma alguma o login e senha (anote em algum lugar), para não perder o acesso da sua maquina com suas informações e dados do servidor.</p>

![3-Configurando VM](https://user-images.githubusercontent.com/58913096/104278988-4c75b500-5488-11eb-96c7-3a7dd9a7b098.png)


Habilitando portas: selecione todas as alternativas que aparecer na opção "Selecione as portas de entrada" e em portas de entrada públicas você permite o acesso das portas selecionadas, para que qualquer um consiga acessar seu servidor. 

Terminando essa parte, pule para avançar discos. Deixe a opção de SSD Premium, ele tem espaço suficiente para armazenar sua base de RP, scripts e arquivos de configuração.

![4-Habilitando ortas](https://user-images.githubusercontent.com/58913096/104279046-6adbb080-5488-11eb-863a-3072480a28b7.png)


Na parte de redes da VM, não altere nada e verifique se as portas estão habilitadas (HTTP, HTTPS, SSH E RDP).
Avance.

![5-Habilitando redes](https://user-images.githubusercontent.com/58913096/104279090-7fb84400-5488-11eb-923e-d7fb13dfd00d.png)


Configure sua base para não ficar online 24hrs nesta pagina de monitoramento, para você não ser cobrado quando seu servidor não estiver sendo utilizado.

Terminando esta parte, pulamos para opção revisar+criar.

![7-Desligamento e backu automatico](https://user-images.githubusercontent.com/58913096/104279141-9363aa80-5488-11eb-80d0-481fa2bac8aa.png)


Se atente o preço que vai ser cobrado pelo seu uso, e revise todas as configurações que você realizou na criação da sua VM. Após isso, clique em criar.

![8 - revisar e criar](https://user-images.githubusercontent.com/58913096/104279213-ae361f00-5488-11eb-8d64-fc626f2f3640.png)

Na pagina inicial do azure, sua base ira aparecer com este icone, selecione a opção e clique em iniciar

![9 - acesso vm](https://user-images.githubusercontent.com/58913096/104279243-bbeba480-5488-11eb-9acc-083d2dbafbe6.png)


Em conectar, selecione a opção RDP e instale na opção "Baixar arquivo RDP"

![10 - iniciar vm](https://user-images.githubusercontent.com/58913096/104279293-d02fa180-5488-11eb-804b-565ba139d216.png)

![12 - Baixar arquivo rd](https://user-images.githubusercontent.com/58913096/104279460-1a188780-5489-11eb-9d98-a4d3434ff0d1.png)

![11 - selecione a ocao RD](https://user-images.githubusercontent.com/58913096/104279372-f35a5100-5488-11eb-8b04-4f94cbffdf87.png)



No seu computador, vá até donwloads (ou no lugar que você instalou sua VM em RDP). Selecione a opção do computador, ele vai abrir uma aba de conexão remota e você clica em conectar.

![13 - Iniciando conexao RD](https://user-images.githubusercontent.com/58913096/104280659-0a9a3e00-548b-11eb-8e9d-a6b98f9ee8bf.png)


Vá até mais opções; usar conta uma conta diferente; digite seu login e senha e clique em ok.

![14 - login](https://user-images.githubusercontent.com/58913096/104280704-1ab21d80-548b-11eb-975b-d5899566861f.png)

![15 - senha](https://user-images.githubusercontent.com/58913096/104280884-5d73f580-548b-11eb-9d94-4ca2c6dc7ec3.png)



Ignore a notificação de certificado e clique em sim.

![15 - ignore certificado](https://user-images.githubusercontent.com/58913096/104280834-492ff880-548b-11eb-9056-b2278db72331.png)


Com a maquina acessada, permita as opções que irão aparecer. Como: descobrimento de redes, que vai aparecer na tela. Acesse o Explorer e instale sua base, XAMP e HEIDISQL.

![16 - maquina acessada](https://user-images.githubusercontent.com/58913096/104281039-990ebf80-548b-11eb-89a0-b4efc3be6c3e.png)



Logo após, pesquise sobre firewall na aba de pesquisa do Windows. Ao entrar na pagina de configuração de firewall, entre em todas as opções circuladas a baixo e deixe desligado (off) todas as opções.

![17 - desabilitando firewall](https://user-images.githubusercontent.com/58913096/104281102-b2177080-548b-11eb-9dc2-73514686b326.png)


Feito isso, confira se todas as opções de firewall estão com um X vermelho sobre elas. Após ter a confirmação que o firewall está desligado, vamos habilitar as portas da VM e permitir o acesso de players no seu servidor de RP.

![18 - desabilitado firewall](https://user-images.githubusercontent.com/58913096/104281131-bcd20580-548b-11eb-863e-f25c68330ce2.png)

![19 - ocoes firewall off](https://user-images.githubusercontent.com/58913096/104281159-cb202180-548b-11eb-8576-4ed3fb31d70a.png)


Na pagina do Azure, vamos acessar o painel de redes, e em seguida, clicar em "Adicionar regra de porta de entrada"

![20 - liberando orta 30120](https://user-images.githubusercontent.com/58913096/104281199-e25f0f00-548b-11eb-8def-30b07699f480.png)


Altere: Intervalos de porta de destino para (30120), prioridade para (310) e o nome do seu servidor. Deixe todas as opções em ANY e permitir.

![21 - orta liberada 30120](https://user-images.githubusercontent.com/58913096/104281234-f4d94880-548b-11eb-9ec4-43bcbc12db77.png)


Após isso, clique em adicionar e seu servidor estará aberto para conexões externas.

![22 - i bulico](https://user-images.githubusercontent.com/58913096/104281241-fa369300-548b-11eb-9574-bb37ea45be41.png)


na mesma aba, seu IP publico vai estar a cima, para acessar seu servidor de RP. Copie seu IP público e no painel do FiveM, coloque connect (e o ip que você copiou).






-------------------------------------------------------------


