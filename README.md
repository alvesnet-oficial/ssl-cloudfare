# ssl-cloudfare

O Cloudfare é CDN (Rede de Entrega de Dados) que melhora a performance do seu site e proporciona uma series de camadas de segurança ao seu site que proporciona um mecanismo de busca melhor nas pesquisas do google, implantando uma nuvem de proxy utilizando a estrutura a nuvem do cloudfare.

- O cloudfare não faz cache de banco de dados
- Mas faz cache de arquivos staticos exemplos: html, css e js
- Se as informações de produto que voce está atualizando no seu site não está atualizando é porque voce está utilizando um 'cache de 
- Cloudfare não é totalmente gratuito. Para sites comerciais (.com, .com.br, .net) ele possuem algus recursos gratuito. Para sites .org não permite utilizar recursos gratuito como instituição educacional e do governo.


# SS/TLS:

Algumas hospedagem trabalha com algumas dessa modalidade abaixo, teremos que consultar nosso provedor de hospedagem:

# Desligado (não seguro): 

Nenhuma criptografia aplicada

# Flexível: 

Criptografa o tráfego de dados apenas entre o navegador do visitante até os servidor da Cloudflare apenas. (não recomendado)

Assim ele vai força o site para https, caso o seu site não esteja abrindo com https é necessário instalar um plugin 'Cloudfare Flexivel'

NOTA 1: Se você quer garantir segurança ate o seu servidor é necessário instalar um plugin do wordpres SSL no seu servidor (recomendado). O plugin Realy Simple  SSL e alterar todos os protocolos http:// para https://.

NOTA 2: Se voce não usa nenhum plugin que forçe os visita para https é necessário ativar essa opção abaixo:

Reescrita Automática de HTTPS - (Ativar)
As Reescritas Automáticas de HTTPS ajudam a corrigir conteúdo misto alterando “http” para “https” para todos os recursos ou links do seu site que podem ser fornecidos com HTTPS.
 
# Completo: 

Criptografa de ponta a ponta usando um certificado autoassinado no servidor

- O SSL Let's encrypt faz a renovação automática sozinho a cada 3 meses. Porem vamos imagina que por algum motivo seu servidor não está conseguindo fazer a renovação automática e está apresentando erro na sua pagina de ssl em vermelho dizendo que o site não é seguro!. Isso é o ssl expirado pois passou o prazo do ssl. 

- O Cloudflare possue essa função 'Completo' que se comunica via ssl com o seu servidor, e seus visitante acessa sua pagina via ssl pelo cloudflare, o cloudfare vai ignorar o alerta se no seu site o ssl estiver expirado como não valido.

# Completo (estrito): 

Criptografa de ponta a ponta, mas requer um certificado CA confiável ou CA de origem do Cloudflare no servidor

* Existe uma criptografia entre 'Cloudfare' e o seu 'Servidor', e entre os 'Visitante' e o 'Cloudfare'.

Requisito:

1. Passo:
- Ativar o Servidor SSL no seu servidor ex: Let's encrypts. Após ativar seu site vai gerar um erro, pois no 'Cloudfare' ate o momento não está ativo nenhum metodo de criptografia. Será necessário ativar o modo 'Completo (restrito). O Sincronismo para ativar o serviço pode demorar até 24hs mas pode ser que ativa a qualquer momento.

2. Passo:
  
  Opção 1:

- Ativar no seu Wordpress: Ativar os links em 'Configuraçoes Gerais' de http// para https://. Quando voce instalar o plugin "Realy Simple SSL' e ja faz essa mundaça de forma transparente se precisa mexer nas 'Configurações Gerais'. E configuração acima é o suficiente.

 Opção 2: (Alternativa)
 
 - Ativar no seu Wordpress: Desativar "Realy Simple SSL'. Atraves da Console Linux do seu servidor lina de comando executar o seguinte:
 
   wp --allow-root search-replace --url=seudomninio.com.br http://seudomninio.com.br https://seudomninio.com.br --path=/var/www/seudomninio.com.br/htdocs

* O comando acima vai procucar todas as ocorrencias do seu dominio com http e vai substitui por https e deixar seu site com o ssl ativo.

NOTA: Se voce usou os passos acima não é necessário ativar essa opção abaixo:

Reescrita Automática de HTTPS - (Desativado)
As Reescritas Automáticas de HTTPS ajudam a corrigir conteúdo misto alterando “http” para “https” para todos os recursos ou links do seu site que podem ser fornecidos com HTTPS.

# SS/TLS\Certificado de Borda:

Para ter uma segurança ainda maior com o site seguir os passos abaixo:

Sempre usar HTTPS - (Ativar)

* Redirecione todas as solicitações com o esquema “http” para “https”. Isso se aplica a todas as solicitações http para a zona.

# HTTP Strict Transport Security (HSTS)\Alterar Ajustes da de HSTS:

* Aplicar a política de segurança da Web para o seu site.

Habilitar HSTS (Strict-Transport-Security) - (Ativar)

* Forneça cabeçalhos HSTS com todas as solicitações HTTPS

Cabeçalho de idade máxima (max-age) - (Ativar 1 mês)

* Especifique a duração em cache dos cabeçalhos HSTS nos navegadores

Aplicar política de HSTS a subdomínios (includeSubDomains) - (Ativar)

* Todos os domínios abaixo dele herdarão os mesmos cabeçalhos HSTS
Atenção: Se algum dos seus subdomínios não suportar HTTPS, ele se tornará inacessível.


Pré-carga - (Ativar)
Permitir que os navegadores pré-carreguem a configuração do HSTS automaticamente
Atenção: A pré-carga pode tornar um site sem suporte HTTPS completamente inacessível.

Plataforma sem sniff - (Ativar)
Envie o cabeçalho “X-Content-Type-Options: nosniff” para evitar que o Internet Explorer e o Google Chrome façam o sniff de MIME fora do Tipo de conteúdo declarado.

# Firewall:

Proteção para seu site.

# Firewall\Bots:

Modo de combate a bots - (Ativar)

* Solicitações de desafio que correspondem aos padrões de bots conhecidos antes de eles acessarem o seu site.

# Speed:

Otimizações ao seu site.

# Speed\Otimizações: 

Minificação Automática - (Ativar)

JavaScript (x)

CSS (x)

HTML (x)

Reduza o tamanho do arquivo do código-fonte no seu site.

Nota: Limpe o cache para que sua alteração entre em vigor imediatamente.

Esta configuração foi alterada pela última vez há poucos segundos

Brotli - (Ativar)
Acelere os tempos de carregamento de página para o tráfego HTTPS do visitante aplicando a compactação Brotli.

***Otimização automática de plataformas para o WordPress - APO - (Analisar como instalar esse plugin no Worpress...)***

***Rocket Loader™ - (Alerta não ativar esse recurso pois ele é incompativel com o elementor) ***

***Móvel - (Alerta não ativar esse recurso pois ele pode quebrar o seu site ***
URL AMP real
Exiba o URL real do seu site em suas páginas AMP, em vez do URL tradicional do cache do Google AMP.
Melhore o tempo de pintura para páginas que incluem JavaScript.
