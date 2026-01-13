Phishing para Captura de Senhas do Facebook

Este projeto foi desenvolvido como parte do Desafio de Projeto do Bootcamp de Cibersegurança da DIO. O objetivo é demonstrar o uso da ferramenta **setoolkit** no Kali Linux para realizar um ataque de engenharia social (Phishing) clonando a página do Facebook.

Ferramentas Utilizadas:
- Kali Linux: Sistema operacional focado em testes de penetração.
- setoolkit (Social Engineering Toolkit): Framework open-source para testes de engenharia social.

Passo a Passo:
Abaixo, detalho o processo realizado para configurar o ataque de phishing.

1. Acesso Root
Para utilizar o setoolkit, é necessário ter permissões administrativas. No terminal do Kali, utilizamos o comando:
bash
sudo su

2. Iniciando o Setoolkit
Com o acesso root, iniciamos a ferramenta:
bash
setoolkit

3. Configurando o Ataque
No menu do setoolkit, seguimos a seguinte sequência de opções para clonar um site:
1. Social-Engineering Attacks (Opção 1)
2. Website Attack Vectors (Opção 2)
3. Credential Harvester Attack Method (Opção 3)
4. Site Cloner (Opção 2)

4. Definindo o IP do Atacante
O sistema solicita o IP para onde as informações coletadas (post back) devem ser enviadas.
- Geralmente, o setoolkit identifica automaticamente o IP da máquina local (ex: 192.168.x.x).
- Confirmamos o IP sugerido pressionando [Enter].

5. Definindo a URL para Clonagem
O sistema solicita a URL do site que desejamos clonar. Para este desafio, utilizamos a página de login do Facebook:
URL: `http://www.facebook.com`

6. Execução e Captura
Após inserir a URL, o setoolkit clona a página e inicia um servidor web na máquina atacante (na porta 80).
- O Cenário: Quando a vítima acessa o IP do atacante (que pode ser mascarado ou enviado via link), ela vê a página de login idêntica à do Facebook.
- A Captura: Ao digitar o usuário e senha na página falsa, o setoolkit captura esses dados e os exibe no terminal do atacante em texto plano (conforme logs abaixo).

Resultados:
text
[*] WEBSERVER IS ON. LISTENING ON 192.168.0.10:80
[*] CLONING THE WEBSITE: [http://www.facebook.com](http://www.facebook.com)
...
POSSIBLE USERNAME FIELD FOUND: email
POSSIBLE PASSWORD FIELD FOUND: pass
...
PARAM: email=vitima@email.com
PARAM: pass=senha123

Autor
Desafio realizado por Bruno Shou
